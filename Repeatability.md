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
hasn't been released yet. Details on snapshots can be found in `lein
help tutorial`, snapshots are by definition non-deterministic.
For this reason, Leiningen will only allow you to depend upon
snapshots if your project's own version is a snapshot.

If you need to make a release and the fix you need hasn't made it into
a release of your dependency, you can lock to a timestamped snapshot
to avoid the repeatability issues. You can find the timestamps for the
snapshots by looking inside your local repo:

    $ ls ~/.m2/repository/slamhound/slamhound/1.1.0-SNAPSHOT/*jar
    slamhound-1.1.0-20110417.030036-2.jar
    slamhound-1.1.0-SNAPSHOT.jar

So now you can replace `[slamhound "1.1.0-SNAPSHOT"]` with
`[slamhound "1.1.0-20110417.030036-2"]` inside project.clj.

## Version Ranges

Version ranges that include versions that haven't been released yet
suffer from the same repeatability issues as snapshots. Ranges that
only cover versions that already exist don't have this problem, but
they do prevent the build from ever working with future versions.
Leiningen will simply refuse to resolve dependency sets that involve
non-overlapping version ranges, so unless you know for a fact that
your project will not work with any future versions of a dependency
you should absolutely avoid ranges.

## Testing

There's been plenty written about nondeterministic tests, and much of
it is not specific to any runtime or language. The key is to ensure
that state from past test runs or development isn't left around to
interfere with future runs. The best way to do this from Clojure is to
take advantage of
[clojure.test/use-fixtures](http://clojuredocs.org/clojure_core/1.3.0/clojure.test/use-fixtures).

## Detecting Non-Repeatability

Non-repeatability usually makes itself known over time, but usually at
the most inopportune or embarrassing moment. You can save a lot of
headache by proactively detecting it with a bit of continuous
integration infrastructure. The most common tools for this are
[[Jenkins]] and [Travis](http://travis-ci.org), the latter being
currently suitable only for open source projects. Travis will run your
tests after every commit in a completely fresh environment, which
helps a lot with dependency issues; the local `~/.m2/repository` cache
is rebuilt afresh every time. With Jenkins you can do that yourself; a
cron job that clears out the local repository every day is probably
