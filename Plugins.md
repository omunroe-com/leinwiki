<!-- -*- auto-fill-function: nil -*-
    In order to support sorting plugins alphabetically, please keep each plugin on its own line. -->

If you’ve created a plugin for Leiningen, please add it here!

_Plugins marked with † have **not** been confirmed to work with Leiningen 2._

## Development Tools

-   [configleaf](https://github.com/davidsantiago/configleaf) Manage Leiningen profiles in a persistent way and access your project map at runtime.
-   [hiccup-bridge](https://github.com/hozumi/hiccup-bridge) Hiccup to html, html to hiccup
-   [lein-aot-filter](https://github.com/pallet/lein-aot-filter) Filtering of AOT compiled class files
-   [lein-checkouts](https://github.com/guv/lein-checkouts)† Build all dependency "checkouts" projects before the current project is build
-   [lein-clean-m2](https://github.com/technomancy/lein-clean-m2) Remove all artifacts from local repo not used by current project
-   [lein-create-template](https://github.com/tcw/lein-create-template) Create Leiningen templates from existing skeleton projects
-   [lein-depgraph](https://github.com/kurtharriger/clojure-dependency-grapher) Generate a namespace dependency graph as an svg file
-   [lein-diagnostics](https://github.com/robwolfe/lein-diagnostics/)† Get diagnostic info regarding versions of libraries
-   [lein-exec](https://github.com/kumarshantanu/lein-exec) Execute Clojure scripts in a project
-   [lein-gentags](https://github.com/snewman/lein-gentags)† Create TAGS files using etags for use in emacs code navigation
-   [lein-git-deps](https://github.com/tobyhede/lein-git-deps)† Pull dependencies via git
-   [lein-git-version](https://github.com/cvillecsteele/lein-git-version) Middleware DRYs up versions by substituting version info found in git tags into project map.
-   [lein-gitify](https://github.com/Raynes/lein-gitify) Create and initialize Github/git in your new Leiningen projects.
-   [lein-iclojure](https://github.com/cosmin/lein-iclojure)† for running an [IClojure](https://github.com/cosmin/IClojure) REPL
-   [lein-jdk-tools](https://github.com/pallet/lein-jdk-tools) Add tools.jar to the classpath
-   [lein-localrepo](https://github.com/kumarshantanu/lein-localrepo) Work with the local Maven repository
-   [lein-maven](https://github.com/pallet/lein-maven) Support for maven projects in checkouts
-   [lein-nevam](https://github.com/thickey/lein-nevam) Convert Maven pom.xml files to project.clj files
-   [lein-notes](https://github.com/myguidingstar/lein-notes) See inline notes from sources
-   [lein-oneoff](https://github.com/mtyaka/lein-oneoff)† Simplify working with one-off, single-file clojure programs
-   [lein-outdated](https://github.com/ato/lein-outdated) List newer available versions of dependencies
-   [lein-project-depends](https://github.com/hugoduncan/lein-namespace-depends)† Output a project’s namespace use/require graph
-   [lein-repls](https://github.com/franks42/lein-repls)† Launch a persistent REPL-server and use the lightweight command-line `cljsh` client to interact
-   [lein-sub](https://github.com/kumarshantanu/lein-sub) Execute tasks on sub-projects
-   [lein-swank](http://github.com/technomancy/swank-clojure) Launch a Swank server for Emacs integration
-   [lein-tarsier](https://github.com/sattvik/lein-tarsier) Add a [VimClojure](http://www.vim.org/scripts/script.php?script_id=2501) server to your project
-   [lein-thrush](https://github.com/technomancy/lein-thrush) Feed the return value of one task into the input of another
-   [lein-vanity](https://github.com/dgtized/lein-vanity) Lines of code statistics for vanity's sake
-   [lein-webrepl](https://github.com/zoka/lein-webrepl) A browser based nREPL interface
-   [slamhound](http://github.com/technomancy/slamhound)† Reconstruct ns forms with needed :use/:require/:import clauses
-   [lein-bikeshed](https://github.com/dakrone/lein-bikeshed) Notify you if your code is bad


## Compilers

-   [lein-aggravate](https://github.com/byels/lein-aggravate) Aggregate & compress .css files, general file aggregation options
-   [lein-antlr](http://github.com/alexhall/lein-antlr)† Generate source code from ANTLR grammars
-   [lein-cljsbuild](http://github.com/emezeske/lein-cljsbuild) Compile ClojureScript automatically upon modification and share code between Clojure and ClojureScript
-   [lein-clr](https://github.com/kumarshantanu/lein-clr) Automate build tasks for ClojureCLR projects on .NET and Mono
-   [lein-cssgenbuild](https://github.com/MichaelDrogalis/lein-cssgenbuild) Generate stylesheets from cssgen
-   [lein-debian](https://github.com/erickg/lein-debian) Package build products and/or dependencies as Debian (.deb) packages
-   [lein-groovyc](https://github.com/kurtharriger/lein-groovyc)† Compile Groovy
-   [lein-lesscss](https://github.com/fmancinelli/lein-lesscss) Compile [Less CSS](http://lesscss.org/) resources.
-   [lein-ragel](https://github.com/llasram/lein-ragel) Compile Ragel sources to Java sources
-   [lein-scalac](https://github.com/technomancy/lein-scalac) Compile Scala
-   [lein-thrift](https://github.com/kurtharriger/lein-thrift)† Generating Thrift sources

## Testing

-   [lein-autoexpect](https://github.com/jakemcc/lein-autoexpect) Watch project for changes and automatically run [expectations](https://github.com/jaycfields/expectations)
-   [lein-autotest](http://github.com/dakrone/lein-autotest)† Start Lazytest's watch on your project for automatic testing on code change
-   [lein-clj-doc-test](https://github.com/newfoundresearch/lein-clj-doc-test)† Enable documentation-based testing like Python's doctest with [clj-doc-test](https://github.com/Kobold/clj-doc-test/)
-   [lein-cucumber](https://github.com/nilswloka/lein-cucumber)† Run clojure-based cucumber-jvm specifications
-   [lein-cuke](http://github.com/mjul/lein-cuke)† Run Cucumber BDD tests
-   [lein-difftest](http://github.com/brentonashworth/lein-difftest) Display diffs when a test fails
-   [lein-expectations](https://github.com/gar3thjon3s/lein-expectations) Run [Expectations](https://github.com/jaycfields/expectations)-based tests
-   [lein-fail-fast](http://github.com/pjstadig/lein-fail-fast)† Stop testing run upon to save time in CI situations
-   [lein-guzheng](http://github.com/dgrnbrg/lein-guzheng) Branch coverage analysis usable with any testing framefork
-   [lein-junit](https://github.com/febeling/lein-junit) Run JUnit tests
-   [lein-midje](https://github.com/marick/lein-midje) Run [Midje](http://github.com/marick/Midje/blob/master/README.md) tests
-   [lein-midje-lazytest](https://github.com/myguidingstar/lein-midje-lazytest) Run Midje/Clojure tests on top of lazytest (Just a meta-package!)
-   [lein-pjotest](https://github.com/jonpither/lein-pjotest) Run test namespaces in parallel with JUnit XML output
-   [lein-play](http://github.com/technomancy/lein-play) Play a different sound at the end of your test runs depending on whether they pass or fail
-   [lein-reload](https://github.com/paraseba/lein-reload)† Reload modified files automatically every time you run your tests
-   [lein-test-bang-bang](https://github.com/joegallo/lein-test-bang-bang)† Run each test namespace in a separate JVM
-   [lein-test-out](https://github.com/arohner/lein-test-out)† Run all tests and outputs to a file in junit XML or TAP format
-   [speclj](https://github.com/slagyr/speclj) (pronounced “speckle”) TDD/BDD framework, with auto-runner, based on [rspec](http://rspec.info/)

## Deployment

-   [lein-beanstalk](https://github.com/weavejester/lein-beanstalk)† Deploy to AWS Elastic Beanstalk
-   [lein-bin](https://github.com/Raynes/lein-bin) Generate cross-platform standalone executables of your project
-   [lein-clojars](https://github.com/ato/lein-clojars) Deploy to Clojars
-   [lein-cloudbees](https://clojars.org/lein-cloudbees) Deploy clojure apps to cloudbees
-   [lein-condor](http://github.com/gilesc/lein-condor)† Execute Clojure code on a Condor cluster
-   [lein-daemon](http://github.com/arohner/lein-daemon)† Run app as a daemon
-   [lein-dist](http://github.com/pallet/lein-dist) Create a standalone tarball of your project source and dependencies
-   [lein-emr](https://github.com/dpetrovics/lein-emr) Create jobflows on Amazon Elastic MapReduce.
-   [lein-hadoop](http://github.com/ndimiduk/lein-hadoop)† Generate a jar containing nested libs as required for hadoop jobs
-   [lein-immutant](https://github.com/immutant/lein-immutant) Manage and deploy applications to an [Immutant](http://immutant.org) server
-   [leiningen-init-script](https://github.com/zkim/leiningen-init-script)† Generate **NIX daemon scripts for your project
-   [lein-init-script](https://github.com/strongh/lein-init-script) Generate **NIX daemon scripts for your project

-   [lein-otf](https://github.com/timmc/lein-otf)† Create non-AOT uberjars
-   [lein-package](https://github.com/pliant/lein-package) Allows for the packaging, installing, and deploying of artifacts besides jars, or multiple artifact projects.
-   [lein-release](https://github.com/relaynetwork/lein-release) Bumps your version number and deploys
-   [lein-tar](http://github.com/technomancy/lein-tar) Create a tarball of your project and its dependencies, formerly lein-release
-   [lein-set-version](https://github.com/pallet/lein-set-version) Sets the version number in your project.clj
-   [lein-sha-version](https://github.com/pallet/lein-sha-version) Middleware to set the project version based on git SHA
-   [pallet-lein](http://github.com/pallet/pallet-lein)† Launch nodes and deploy "crate" packages to the cloud

## Web

-   [lein-axis](https://github.com/jaley/lein-axis)† Generate Apache Axis stubs from a WSDL file
-   [lein-beanstalk](https://github.com/weavejester/lein-beanstalk) Deploy to Amazon’s Elastic Beanstalk service
-   [lein-conjure](http://github.com/macourtney/Conjure)† Create a Conjure project and run it
-   [lein-gaeshi](https://github.com/slagyr/gaeshi) Google App Engine webs apps using Joodo. 
-   [lein-gwt](http://github.com/teropa/lein-gwt)† Run the Google Web Toolkit compiler
-   [lein-heroku](https://github.com/technomancy/lein-heroku) Generate and manage Heroku apps.
-   [lein-joodo](https://github.com/slagyr/joodo) Simple web app library.  Tasks to create, test, generate, your code.
-   [lein-ring](https://github.com/weavejester/lein-ring) Work with web applications using Ring
-   [lein-servlet](https://github.com/kumarshantanu/lein-servlet) Work with servlet-based webapps
-   [lein-war](https://github.com/pliant/lein-war) Extends lein-ring to create compliant WARs for any servlet container.(2.0+)

## Databases

-   [lein-flyway](https://github.com/teropa/lein-flyway)† Run [Flyway database migrations](http://code.google.com/p/flyway)
-   [lein-lb](https://bitbucket.org/kumarshantanu/lein-lb)† Database migrations using [Clj-Liquibase](https://bitbucket.org/kumarshantanu/clj-liquibase)
-   [drift](http://github.com/macourtney/drift)† Create and run Rails like database migrations in Clojure
-   [lein-embongo](https://github.com/joelittlejohn/lein-embongo) Create a managed/embedded instance of MongoDB during a lein build (e.g. for integration testing).
-   [lein-dbmaintain](https://github.com/mysema/lein-dbmaintain) DbMaintain integration for Leiningen

## Documentation

-   [lein-autodoc](https://github.com/tomfaulhaber/lein-autodoc)† Generate autodoc documentation
-   [lein-docbkx](https://github.com/kumarshantanu/lein-docbkx)† Render Docbook XML documents as PDF, EPUB, HTML etc. using Docbkx-tools
-   [lein-html5-docs](https://github.com/tsdh/lein-html5-docs) Generate HTML5 API docs
-   [lein-licenses](https://github.com/technomancy/lein-licenses) List licenses of all dependencies
-   [lein-margauto](https://github.com/kyleburton/lein-margauto)† Watches your source directories for changes to your clojure source files and rebuilds the Marginalia documentation whenever you update your source code
-   [lein-marginalia](https://github.com/fogus/lein-marginalia) Generate [Marginalia](https://github.com/fogus/marginalia) documentation
-   [lein-mustache](https://github.com/achin/lein-mustache) Evaluate Mustache templates with Clojure data files (e.g. for creating templatized documentation)
-   [lein-precate](https://github.com/technomancy/lein-precate) Transform project.clj into Leiningen 2.x-compatible form.

## Deprecated
-   [fw1-template](https://github.com/seancorfield/fw1-template) Create [FW/1](https://github.com/seancorfield/fw1-clj) projects (use `lein new fw1 myapp` instead)
-   [lein-eclipse](https://github.com/abrenk/lein-eclipse)† Create Eclipse project descriptor files (use recent CounterClockwise)
-   [lein-nailgun](https://github.com/mrowl/lein-nailgun)† Launch a vimclojure nailgun server (use lein-tarsier)
-   [lein-noir](https://github.com/ibdknox/lein-noir) Create and manage [Noir](http://www.webnoir.org) projects (use `new` task)
-   [leiningen-war](http://github.com/alienscience/leiningen-war)† Create WAR files for use in servlet containers (use lein-ring)
-   [radagast](http://github.com/Seajure/radagast)† Get simplistic test coverage (use guzheng)
-   [lein-idea](https://bitbucket.org/bkumar/lein-idea) Generates Intellij IDEA project files

## Merged into Leiningen

-   [lein-javac](https://github.com/antoniogarrote/lein-javac) For compiling Java source (1.4+)
-   [lein-multi](http://github.com/maravillas/lein-multi) Run tasks against multiple dependency sets (such as multiple Clojure versions) at once (2.0+)
-   [lein-newnew](https://github.com/Raynes/lein-newnew) Next-generation `lein new` supporting custom project skeletons (2.0+)
-   [lein-plugin](http://github.com/trptcolin/lein-plugin) Manage plugins (1.4+)
-   [lein-retest](http://github.com/technomancy/lein-retest) Run only the test namespaces which failed last time around (1.6+)
-   [lein-run](http://github.com/sids/lein-run) Call -main functions from the command-line (1.4+)
-   [lein-search](http://github.com/Licenser/lein-search) Search remote repositories for artifacts (1.6+)