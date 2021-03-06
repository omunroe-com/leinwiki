Part of what makes Leiningen's boot take a while is the fact that
Leiningen's code is completely isolated from project code. This means
that two JVMs are necessary to complete any task that has to execute
anything in the project: one for Leiningen itself, and a subprocess
for the project. There are various strategies to address this. Some of
them can provide cumulative benefit, while some are mutually exclusive.

## Don't Exit

The most obvious is simply to adjust your workflow so you don't start
Leiningen very often. Most people simply launch a REPL once and leave
it up for their whole hacking session. You still need to restart when
you change your `:dependencies`, but working from within a single REPL
session is a lot more convenient than running `lein` afresh over and
over.

Of course, as you build up state in your process during development,
there's a chance that old definitions you've removed that stick around
in memory will cause bugs, so it's always a good idea to do a fresh
`lein test` run before any major milestones like merging a
long-running branch or deploying.

## Fast Trampoline

As of Leiningen 2.0.0 you can perform fast trampolines. You can think
of any task invocation as a pure-ish function of the command-line
arguments, project.clj file, and repository state. Like any function,
one way to optimize it is memoization. Setting the
`LEIN_FAST_TRAMPOLINE` environment variable causes the `bin/lein`
script to memoize all trampoline calls by saving off the `java`
process invocation to disk upon the first run. This allows
successive runs to skip launching a JVM for Leiningen entirely, so
you will only have to wait for your own application's boot time.

Changing `project.clj` will invalidate the cache, as will deleting the
`target` directory. Also note that only `trampoline` calls will be
memoized. Since Leiningen never gets a chance to run itself, it won't
check for new snapshot versions.

## Tiered Compilation

Leiningen 2 uses a JVM feature called Tiered Compilation which allows
the JVM to switch between compilation strategies at runtime; it can
begin with a quick-start setting and switch to optimized compilation
later once it has identified which sections of the code are hotspots.

Leiningen 2.1.0 onward get a speed boost by disabling the optimized
compilation (which only benefits long-running processes) for both 
your project and Leiningen itself.

Be aware that this can negatively affect performance in the long run 
(or lead to inaccurate benchmarking results).  If you do have a 
long-running processes and want the JVM to fully optimize, you can 
disable tiered compilation by either:

    $ export LEIN_JVM_OPTS=

or in `project.clj` with:

    :jvm-opts ^:replace []

## Eval in nREPL

In Leiningen 2.1.0 and on you can add `:eval-in :nrepl` to re-use an
existing project JVM over nREPL rather than launching a new one. This
acts a bit like Cake's persistent JVMs feature, but you have to manage
the lifecycle of the project JVM yourself. This can be done by simply
running `lein repl` in a separate terminal.

This will still incur the penalty for launching Leiningen itself, just
not the project JVM. If Leiningen determines there's no project nREPL
server to connect to it will fall back to launching a subprocess. Note
that it does not stack with fast trampolines.

## Avoiding nREPL with clojure.main

A good portion of the delay involved in getting a repl up comes from
launching a `tools.nrepl` server. Clojure ships with its own primitive
repl, that lacks fancy features but still gets the basics done. In
cases were you're already using fast trampoline (see above), using the
`clojure.main` repl instead of nREPL can boost launch time by a factor
of up to 5x:

    $ LEIN_FAST_TRAMPOLINE=y lein trampoline run -m clojure.main
    Clojure 1.6.0
    user=> 

Note that this is not compatible with nrepl-based tools like cider or
grenchman. It also lacks tab completion and line editing. The latter
can be addressed using `rlwrap` or by running it inside Emacs using
`M-x shell` or `inferior-lisp`.

## Drip

[Drip](https://github.com/ninjudd/drip) is a script intended to speed
up JVM start times. Installation details and an explanation of how
Drip works are in the
[Drip Readme](https://github.com/ninjudd/drip/blob/master/README.md).
Leiningen will make use of a Drip installation if the `LEIN_JAVA_CMD`
environment variable is set to the location of the drip script.

## Eval in Classloader

Setting `:eval-in :classloader` will run the project's code in the
same JVM as Leiningen, albeit in a separate classloader.  However, the
bootclasspath optimizations used by Leiningen can interfere with
classloader isolation, so this mode is not recommended.  If you do use
this mode and start to experience strange, seemingly inexplicable
issues, then remove this setting.

## Disable bytecode verification

Normally all code that's loaded runs thru the bytecode verifier, which
is very I/O heavy. It's vanishingly unlikely that the bytecode
verifier will actually find any problems that Leiningen's own
checksum mechanism wouldn't, so you can turn it off with this:

    :jvm-opts ["-Xverify:none"]

## Check your :main

When starting the REPL, Leiningen loads the project's `:main`
namespace.  If the `:main` namespace takes significant time to load,
the user's perception is that Leiningen is slow.

## Grenchman

[Grenchman](http://leiningen.org/grench.html) is a fast-launching
command-line client that can connect to already-running nREPL servers
to evaluate code. You can use it both to avoid startup time of
Leiningen itself (`grench lein $TASK`) or to connect directly to a
project repl server.
