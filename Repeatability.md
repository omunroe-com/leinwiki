Leiningen is a tool designed around project automation. But without
repeatability, automation is worthless.

You can think of a build as a function of the current state of the
project, with the repositories referenced by the project's
configuration serving as its lexical environment. The return value is
the output, exit code, and artifact files produced.

Anything that increases the chance of the build behaving differently
on different machines is repeatability poison and should be
eliminated. Here are a few of the most common offenders.

## User-level Repositories

If you were after repeatability above all else, you would want each
build to fetch all its dependencies from the repositories configured
in project.clj every time. However, this is too slow to be practical,
so dependencies get cached in the local repository inside `~/.m2/`.

One common problem is to check in configuration that accidentally
depends upon the local repository on your own machine; perhaps you
pulled in a dependency X from a third-party repo like Sonatype while
working on project A and then declared X as a dependency of project B
without adding Sonatype to project B's repository list. As soon as
someone tries working on project B on another machine that hasn't had
its local repo primed the same way it will fail.

In Leiningen 2 it's possible to add a `:repositories` key to your
`:user` profile, but this exacerbates all the same problems you get
with the local repository. You'll get a warning if you try to do this.

## Free-Floating Jars

It may be desirable to add dependencies on jars which haven't been
published to any repository. While it's possible to install them
locally with things like
[lein-localrepo](https://github.com/kumarshantanu/lein-localrepo),
doing so adds the requirement of a manual step to your build, which is
counter to our goals of repeatability and automation. It may be
acceptable if you are working on a project in isolation rather than on
a team, but in most cases it's best to get it into a repository.

If the code is public, you should open a bug report with upstream to
get them to publish it in a public repository like Clojars, Sonatype,
or Maven Central, depending on the project. If they are resistant or
too slow it's always possible to publish "Clojars forks"; see `lein
help deploying` for further details there.

Private jars are similar; if your company has an internal Nexus or
Archiva server that's a natural place for them. If you'd like
something simpler you can host them on a
[private S3 bucket](https://github.com/technomancy/s3-wagon-private).

## Snapshot Versions

Sometimes it's necessary to include a dependency on software that
hasn't been released yet; details on snapshots can be found in `lein
help tutorial`. Snapshots are by definition non-deterministic, and
for this reason Leiningen will only allow you to depend upon
snapshots if your project's version is itself a snapshot.

If you need to make a release and the fix you need hasn't made it into
a release of your dependency, you can lock to a timestamped snapshot
to avoid the repeatability issues. You can find the timestamps for the
snapshots with `lein deps :tree`:

    $ lein deps :tree
     [org.clojure/clojure "1.4.0"]
     [compojure "1.1.0-20120509.203749-1"]
       [clout "1.0.1"]
       [...]

So now you can replace `[compojure "1.1.0-SNAPSHOT]` with
`[compojure "1.1.0-20120509.203749-1"]` inside project.clj. If you use
Leiningen 1.x you can find the number in the filename of the jar
inside the `lib` directory.

## Version Ranges

Version ranges that include versions that haven't been released yet
suffer from the same repeatability issues as snapshots. Ranges that
only cover versions that already exist don't have this problem, but
they do prevent the build from ever working with future versions.
Leiningen will simply refuse to resolve dependency sets that involve
non-overlapping version ranges. In addition, version ranges introduce
unexpected quirks in the dependency resolution process due to their
surprising semantics around precedence; it's
[recommended that you avoid them entirely](http://nelsonmorris.net/2012/07/31/do-not-use-version-ranges-in-project-clj.html).

## Testing

There's been plenty written about nondeterministic tests, and much of
it is not specific to any runtime or language. The key is to ensure
that state from past test runs or development isn't left around to
interfere with future runs. The best way to do this from Clojure is to
take advantage of
[clojure.test/use-fixtures](http://clojuredocs.org/clojure_core/1.3.0/clojure.test/use-fixtures)
to clear out things like directories on disk used for tempfiles,
database tables, or in-memory refs/atoms.

    (use-fixtures :each (fn [f]
                          (delete-file-recursively
                           (file "test_projects" "sample" "classes") :silently)
                          (f)))

## Detecting Non-Repeatability

Non-repeatability usually makes itself known over time, but usually at
the most inopportune or embarrassing moment. You can save a lot of
headache by proactively detecting it with a bit of continuous
integration infrastructure. The most common tools for this are
[Jenkins](https://wiki.jenkins-ci.org/display/JENKINS/leiningen+plugin)
and [Travis](http://travis-ci.org), the latter being currently
suitable only for open source projects. Travis will run your tests
after every commit in a completely fresh environment, which helps a
lot with dependency issues; the local `~/.m2/repository` cache is
rebuilt afresh every time. With Jenkins you can do that yourself; a
cron job that clears out the local repository every day is probably
your best bet.

Forgetting to check in files is another common source of
non-repeatability, but it can easily be addressed with
[pre-commit hooks](http://book.git-scm.com/5_git_hooks.html).
