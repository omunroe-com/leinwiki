If you’ve created a plugin for Leiningen, please add it here!

## Development Tools

-   [drift](http://github.com/macourtney/drift) Create and run Rails
    like database migrations in Clojure.
-   [lein-antlr](http://github.com/alexhall/lein-antlr) Generate source
    code from ANTLR grammars.
-   [lein-checkouts](https://github.com/guv/lein-checkouts) A leiningen
    plugin to build all dependency “checkouts” projects before the
    current project is build.
-   [lein-cljsbuild](http://github.com/emezeske/lein-cljsbuild) Compile
    ClojureScript automatically upon modification. Includes support for
    sharing code between Clojure and ClojureScript.
-   [lein-clojurescript](http://github.com/bartonj/lein-clojurescript)
    Compile clojurescript.
-   [lein-diagnostics](https://github.com/robwolfe/lein-diagnostics/)
    Get diagnostic info regarding versions of libraries.
-   [lein-eclipse](https://github.com/abrenk/lein-eclipse) Create
    Eclipse project descriptor files.
-   [lein-exec](https://github.com/kumarshantanu/lein-exec) Execute
    Clojure scripts in a project
-   [lein-flyway](https://github.com/teropa/lein-flyway) for running the
    [Flyway database migration
    framework](http://code.google.com/p/flyway)
-   [lein-groovyc](https://github.com/kurtharriger/lein-groovyc) for compiling groovy source code
-   [lein-jit](https://github.com/timmc/lein-jit) for creating non-AOT uberjars
-   [lein-lb](https://bitbucket.org/kumarshantanu/lein-lb) Database
    migrations using
    [Clj-Liquibase](https://bitbucket.org/kumarshantanu/clj-liquibase)
-   [lein-localrepo](https://github.com/kumarshantanu/lein-localrepo)
    Work with local Maven repository
-   [lein-multi](http://github.com/maravillas/lein-multi) Run tasks
    against multiple dependency sets (such as multiple Clojure versions)
    at once.
-   [lein-nailgun](https://github.com/mrowl/lein-nailgun) Launch a
    vimclojure nailgun server.
-   [lein-nrepl](https://github.com/stephenalindsay/lein-nrepl) Launch
    an nREPL server.
-   [lein-notes](https://github.com/taweili/lein-notes) See inline notes
    from sources.
-   [lein-oneoff](https://github.com/mtyaka/lein-oneoff) Simplify
    working with one-off, single-file clojure programs.
-   [lein-project-depends](https://github.com/hugoduncan/lein-namespace-depends)
    Output a project’s namespace use/require graph.
-   [lein-sub](https://github.com/kumarshantanu/lein-sub) Execute tasks
    on sub-projects
-   [slamhound](http://github.com/technomancy/slamhound) Reconstruct ns
    forms with needed :use/:require/:import clauses.
-   [swank-clojure](http://github.com/technomancy/swank-clojure) Launch
    a Swank server for Emacs integration.
-   [spawn](https://github.com/levand/spawn) A leiningen plugin for easy
    project and code generation in Clojure
-   [lein-thrift](https://github.com/kurtharriger/lein-thrift) for generating thrift sources

## Testing

-   [lein-autotest](http://github.com/dakrone/lein-autotest) Starts
    Lazytest’s watch on your project for automatic testing on code
    change.
-   [lein-autoexpect](https://github.com/jakemcc/lein-autoexpect) Watches
    project for changes and automatically runs [expectations](https://github.com/jaycfields/expectations)
-   [lein-cuke](http://github.com/mjul/lein-cuke) Run Cucumber BDD
    tests.
-   [lein-difftest](http://github.com/brentonashworth/lein-difftest)
    Display diffs when a test fails.
-   [lein-fail-fast](http://github.com/pjstadig/lein-fail-fast) Stop
    testing run upon to save time in CI situations.
-   [lein-junit](https://github.com/febeling/lein-junit) Run JUnit
    tests.
-   [lein-midje](https://github.com/marick/lein-midje) Run
    [Midje](http://github.com/marick/Midje/blob/master/README.md) tests.
-   [lein-play](http://github.com/technomancy/lein-play) Play a
    different sound at the end of your test runs depending on whether
    they pass or fail.
-   [lein-reload](https://github.com/paraseba/lein-reload) Reload
    modified files automatically every time you run your tests
-   [lein-test-bang-bang](https://github.com/joegallo/lein-test-bang-bang)
    Run each test namespace in a separate JVM.
-   [lein-test-out](https://github.com/arohner/lein-test-out) Run all
    tests and outputs to a file in junit XML or TAP format.
-   [radagast](http://github.com/Seajure/radagast) Get simplistic test
    coverage.
-   [speclj](https://github.com/slagyr/speclj) (pronounced “speckle”)
    TDD/BDD framework, with auto-runner, based on
    [rspec](http://rspec.info/)
-   [lein-clj-doc-test](https://github.com/newfoundresearch/lein-clj-doc-test)
    Plugin derived from
    [clj-doc-test](https://github.com/Kobold/clj-doc-test/), which
    enables document based testing like Python’s doctest

## Deployment

-   [lein-clojars](https://github.com/ato/lein-clojars) Deploy to
    Clojars.
-   [lein-daemon](http://github.com/arohner/lein-daemon) Run app as a
    daemon.
-   [lein-hadoop](http://github.com/ndimiduk/lein-hadoop) Generate a jar
    containing nested libs as required for hadoop jobs.
-   [lein-condor](http://github.com/gilesc/lein-condor) Execute Clojure
    code on a Condor cluster.
-   [lein-init-script](http://github.com/zkim/leiningen-init-script)
    Generate **NIX daemon scripts for your project.\
    ** [lein-tar](http://github.com/technomancy/lein-tar) Create a
    tarball of your project and its dependencies. (formerly
    lein-release)
-   [pallet-lein](http://github.com/pallet/pallet-lein) Launch nodes and
    deploy “crate” packages to the cloud.
-   [lein-bin](https://github.com/Raynes/lein-bin) Generate
    cross-platform standalone executables of your project.

## Web

-   [lein-noir](https://github.com/ibdknox/lein-noir) Create and manage
    [Noir](http://www.webnoir.org) projects
-   [lein-beanstalk](https://github.com/weavejester/lein-beanstalk)
    Deploy to Amazon’s Elastic Beanstalk service.
-   [lein-conjure](http://github.com/macourtney/Conjure) Create a
    Conjure project and run it.
-   [lein-gwt](http://github.com/teropa/lein-gwt) Run the Google Web
    Toolkit compiler.
-   [lein-ring](https://github.com/weavejester/lein-ring) Ring plugin.
-   [leiningen-war](http://github.com/alienscience/leiningen-war) Create
    WAR files for use in servlet containers.

## Documentation

-   [lein-marginalia](https://github.com/fogus/lein-marginalia)
    Leiningen Plugin for
    [Marginalia](https://github.com/fogus/marginalia)
-   [lein-margauto](https://github.com/kyleburton/lein-margauto)
    Leiningen Plugin for
    [Marginalia](https://github.com/fogus/marginalia) that watches your
    source directories for changes to your clojure source files and
    rebuilds the Marginalia documentation whenever you update your
    source code.

## Merged into Leiningen

-   [lein-javac](https://github.com/antoniogarrote/lein-javac) For
    compiling Java source (1.4+)
-   [lein-plugin](http://github.com/trptcolin/lein-plugin) A plugin to
    manage plugins. (1.4+)
-   [lein-run](http://github.com/sids/lein-run) Call -main functions
    from the command-line. (1.4+)
-   [lein-retest](http://github.com/technomancy/lein-retest) Run only
    the test namespaces which failed last time around. (1.6+)
-   [lein-search](http://github.com/Licenser/lein-search) Search remote
    repositories for artifacts. (1.6+)
