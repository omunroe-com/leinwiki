<!-- -*- auto-fill-function: nil -*-
    In order to support sorting plugins alphabetically, please keep each plugin on its own line. -->

If you’ve created a [plugin](https://github.com/technomancy/leiningen/blob/master/doc/PLUGINS.md) for Leiningen, please add it here!

Please note that inclusion on this list does not constitute endorsement by the Leiningen maintainers.

## Development Tools

-   [configleaf](https://github.com/davidsantiago/configleaf) Build profiles and access to project.clj at runtime. (see also 'slothcfg', an updated fork)
-   [datomic-schema-grapher](https://github.com/felixflores/datomic_schema_grapher) A library and lein plugin for graphing datomic schemas
-   [hiccup-bridge](https://github.com/hozumi/hiccup-bridge) Hiccup to html, html to hiccup
-   [lein-4clj](https://github.com/aengelberg/lein-4clj) An unofficial companion to [4clojure](http://www.4clojure.com), a Clojure kata site.
-   [lein-amp](https://github.com/pmonks/lein-amp) Leiningen plugin for generating Alfresco Module Package (AMP) files.
-   [lein-ancient](https://github.com/xsc/lein-ancient) Check your projects and plugins for outdated dependencies.
-   [lein-annotations](https://github.com/bbatsov/lein-annotations) Displays comment annotations in your project.
-   [lein-aot-filter](https://github.com/pallet/lein-aot-filter) Filtering of AOT compiled class files
-   [lein-auto](https://github.com/weavejester/lein-auto) Automatically perform a task when source files change
-   [lein-autoreload](https://github.com/pyronicide/lein-autoreload) Reload your source in the background while running the repl.
-   [lein-bikeshed](https://github.com/dakrone/lein-bikeshed) Notify you if your code is bad
-   [lein-capsule](https://github.com/circlespainter/lein-capsule) [Capsule](http://www.capsule.io) plugin for Leiningen
-   [lein-cascade](https://github.com/kumarshantanu/lein-cascade) Execute cascading task dependencies
-   [lein-checkall](https://github.com/itang/lein-checkall) lein check && lein kibit && lein eastwood && lein bikeshed
-   [lein-checkouts](https://github.com/guv/lein-checkouts) Build all dependency "checkouts" projects before the current project is build
-   [lein-chromebuild](https://github.com/clumsyjedi/lein-chromebuild) Create chrome extensions from clojurescript
-   [lein-clean-m2](https://github.com/technomancy/lein-clean-m2) Remove all artifacts from local repo not used by current project
-   [lein-collisions](https://github.com/webnf/lein-collisions) Find conflicting files on the classpath
-   [lein-cooper](https://github.com/kouphax/lein-cooper) Foreman style plugin for Leiningen for running long running dev tasks in parallel. 
-   [lein-cprint](https://github.com/greglook/lein-cprint) Like lein-pprint, but with color.
-   [lein-create-template](https://github.com/tcw/lein-create-template) Create Leiningen templates from existing skeleton projects
-   [lein-depgraph](https://github.com/kurtharriger/clojure-dependency-grapher) Generate a namespace dependency graph as an svg file
-   [lein-eastwood](https://github.com/jonase/eastwood) A Clojure linting tool that inspects Clojure code and reports possible problems.
-   [lein-exec](https://github.com/kumarshantanu/lein-exec) Execute Clojure scripts in a project
-   [lein-expand-resource-paths](https://github.com/dchelimsky/lein-expand-resource-paths) Expand glob patterns in `:resource-paths` to work alongside alternative dependency managers
-   [lein-extend-cp](https://github.com/nickgieschen/lein-extend-cp) Adds paths to the classpath
-   [lein-externs](https://github.com/ejlo/lein-externs) Generate externs for your ClojureScript project
-   [lein-cljs-externs](https://github.com/bbbates/lein-cljs-externs) Generate externs for your Clojurescript project, specified via metadata
-   [lein-file-replace](https://github.com/jcrossley3/lein-file-replace) Replace text in files with other text, possibly from a project map
-   [lein-filegen](https://github.com/ThoughtWorksInc/lein-filegen) Generate files from data and a template
-   [lein-fore-prob](https://github.com/bfontaine/probs-from-4clj) Import problems from [4clojure](http://www.4clojure.com)
-   [lein-git-deps](https://github.com/tobyhede/lein-git-deps) Pull dependencies via git
-   [lein-git-version](https://github.com/cvillecsteele/lein-git-version) Middleware DRYs up versions by substituting version info found in git tags into project map.
-   [lein-githooks](https://github.com/gmorpheme/lein-githooks) Manage git hooks in `project.clj`.
-   [lein-gitify](https://github.com/Raynes/lein-gitify) Create and initialize Github/git in your new Leiningen projects.
-   [lein-grep](https://github.com/cldwalker/lein-grep) Improved repository searching built off the search subcommand.
-   [lein-hadoop-cluster](https://github.com/llasram/lein-hadoop-cluster) Run Leiningen tasks with the configuration necessary to access a live Hadoop cluster.
-   [lein-hiera](https://github.com/greglook/lein-hiera) Generate namespace dependency graphs from Leiningen projects.
-   [lein-idefiles](https://github.com/kumarshantanu/lein-idefiles) Generate IDE files (Eclipse, IDEA) for Leiningen projects
-   [lein-inject](https://github.com/palletops/lein-inject) Inject vars into convenience namespaces for the REPL.
-   [lein-instant-cheatsheet](https://github.com/cammsaul/instant-clojure-cheatsheet) Generate a cheatsheet for your project and dependencies
-   [lein-javac-resources](https://github.com/kumarshantanu/lein-javac-resources) Copy resources from `:java-source-paths` to compile path (hooks into `lein javac`)
-   [lein-jdk-tools](https://github.com/pallet/lein-jdk-tools) Add tools.jar to the classpath
-   [lein-jshint](https://github.com/vbauer/lein-jshint) static code analysis for JS, based on JSHint
-   [lein-jslint](https://github.com/vbauer/lein-jslint) static code analysis for JS, based on JSLint
-   [lein-kibit](https://github.com/jonase/kibit) static code analysis to find more idiomatic ways to write your Clojure code.
-   [lein-libdir](https://github.com/djpowell/lein-libdir) Copy dependencies to a 'lib' folder in your project
-   [lein-localrepo](https://github.com/kumarshantanu/lein-localrepo) Work with the local Maven repository
-   [lein-maven](https://github.com/pallet/lein-maven) Support for maven projects in checkouts
-   [lein-modules](https://github.com/jcrossley3/lein-modules) An alternative to Maven multi-module projects
-   [lein-nevam](https://github.com/thickey/lein-nevam) Convert Maven pom.xml files to project.clj files
-   [lein-notes](https://github.com/myguidingstar/lein-notes) See inline notes from sources
-   [lein-ns-dep-graph](https://github.com/hilverd/lein-ns-dep-graph) Show namespace dependencies of Clojure project sources as a graph
-   [lein-oneoff](https://github.com/mtyaka/lein-oneoff) Simplify working with one-off, single-file clojure programs
-   [lein-open](https://github.com/cldwalker/lein-open) Open any dependency or installed jar in an editor.
-   [lein-parent](https://github.com/achin/lein-parent) Inherit properties from a parent project
-   [lein-pdo](https://github.com/Raynes/lein-pdo) Run lein tasks concurrently in parallel
-   [lein-plz](https://github.com/johnwalker/lein-plz) Add dependencies to projects quickly
-   [lein-resource](https://github.com/m0smith/lein-resource) Copy files and transform using [stencil](https://github.com/davidsantiago/stencil)
-   [lein-shell](https://github.com/hyPiRion/lein-shell) Run sub-processes from within Leiningen.
-   [lein-sub](https://github.com/kumarshantanu/lein-sub) Execute tasks on sub-projects
-   [lein-tarsier](https://github.com/sattvik/lein-tarsier) Add a [VimClojure](http://www.vim.org/scripts/script.php?script_id=2501) server to your project
-   [lein-teamcity](https://github.com/nd/lein-teamcity) Add an on-the-fly stages, artifacts and tests reporting in TeamCity
-   [lein-thrush](https://github.com/technomancy/lein-thrush) Feed the return value of one task into the input of another
-   [lein-try](https://github.com/rkneufeld/lein-try) Try out libraries without creating a dummy project/dependency.
-   [lein-ubersource](https://github.com/puppetlabs/lein-ubersource) Download the source code for all of the project's (transitive) dependencies.
-   [lein-vanity](https://github.com/dgtized/lein-vanity) Lines of code statistics for vanity's sake
-   [lein-var-file](https://github.com/orend/lein-var-file) Creates an environment variables file. Works great with [environ](https://github.com/weavejester/environ) and useful when running Docker containers.
-   [lein-vertx](https://github.com/isaiah/lein-vertx) Develop vertx applications in clojure
-   [lein-webdav](https://github.com/tobias/lein-webdav) Enables uploading of deployments to webdav repos
-   [lein-webrepl](https://github.com/zoka/lein-webrepl) A browser based nREPL interface
-   [lein-whimrepl](https://github.com/malyn/lein-whimrepl) Start a REPL session in a Vim-targetable server for use with [vim-slime](https://github.com/jpalardy/vim-slime).
-   [reloadable-app](https://github.com/mowat27/reloadable-app) Leiningen template for a new component based app implementing the reloaded workflow.
-   [slothcfg](https://github.com/taoeffect/slothcfg) Build profiles and access to project.clj at runtime. Updated fork of 'configleaf'.
-   [varspotting](https://github.com/michalmarczyk/varspotting) Count public Vars meeting certain criteria (holding functions, macros etc.)
-   [mranderson](https://github.com/benedekfazekas/mranderson) Download and use some dependencies as source.
-   [gargamel](https://github.com/MailOnline/gargamel) generates pretty (with links etc) changelog based on git commit messages in multiple formats
-   [ultra](https://github.com/venantius/ultra) A Leiningen plugin for a superior development environment

## Compilers

-   [funcgo-lein](https://github.com/eobrain/funcgo-lein) Funcgo is a compiler that converts Functional Go into Clojure, to run on the JVM or as JavaScript.
-   [lein-aggravate](https://github.com/byels/lein-aggravate) Aggregate & compress .css files, general file aggregation options
-   [lein-antlr](https://github.com/alexhall/lein-antlr) Generates source code from ANTLR grammars
-   [lein-beaver](https://github.com/quoll/lein-beaver) Generates source code from Beaver/JFlex grammars
-   [lein-cl2c](http://github.com/chlorinejs/lein-cl2c) Compile Chlorine (a subset of Clojure) and Hiccup to Javascript/HTML files
-   [lein-cljsbuild](http://github.com/emezeske/lein-cljsbuild) Compile ClojureScript automatically upon modification and share code between Clojure and ClojureScript
-   [lein-clr](https://github.com/kumarshantanu/lein-clr) Automate build tasks for ClojureCLR projects on .NET and Mono
-   [lein-coffeescript](https://github.com/vbauer/lein-coffeescript) Compile [CoffeeScript](http://coffeescript.org)
-   [lein-cssgenbuild](https://github.com/MichaelDrogalis/lein-cssgenbuild) Generate stylesheets from cssgen
-   [lein-debian](https://github.com/erickg/lein-debian) Package build products and/or dependencies as Debian (.deb) packages
-   [lein-droid](https://github.com/clojure-android/lein-droid) Compile Android projects
-   [lein-fruit](https://github.com/oakes/lein-fruit) Compile iOS projects
-   [lein-groovyc](https://github.com/kurtharriger/lein-groovyc) Compile Groovy
-   [lein-lesscss](https://github.com/fmancinelli/lein-lesscss) Compile [Less CSS](http://lesscss.org/) resources.
-   [lein-less4j](https://github.com/Deraen/lein-less4j) Compile [Less CSS](http://lesscss.org/) using [Less4j](https://github.com/SomMeri/less4j). Supports reading imports from classpath.
-   [lein-ragel](https://github.com/llasram/lein-ragel) Compile Ragel sources to Java sources
-   [lein-sassy](https://github.com/vladh/lein-sassy) Use [Sass](http://sass-lang.com/) with Clojure.
-   [lein-scalac](https://github.com/technomancy/lein-scalac) Compile Scala
-   [lein-thriftc](https://github.com/xsc/lein-thriftc) Compile Thrift
-   [lein-typescript](https://github.com/vbauer/lein-typescript) Compile [TypeScript](https://github.com/Microsoft/TypeScript)
-   [lein-zinc](https://github.com/k2n/lein-zinc) Compile Scala and Java with [Typesafe zinc](https://github.com/typesafehub/zinc) incremental compiler.

## Testing

-   [lein-autoexpect](https://github.com/jakemcc/lein-autoexpect) Watch project for changes and automatically run [expectations](https://github.com/jaycfields/expectations)
-   [lein-cloverage](https://github.com/lshift/cloverage) Generate cloverage coverage reports
-   [lein-cucumber](https://github.com/nilswloka/lein-cucumber) Run clojure-based cucumber-jvm specifications
-   [org.clojars.punkisdead/lein-cucumber](https://github.com/punkisdead/lein-cucumber) Run clojure-based cucumber-jvm specifications (an up to date fork of the lein-cucumber plugin)
-   [lein-difftest](http://github.com/brentonashworth/lein-difftest) Display diffs when a test fails
-   [lein-expectations](https://github.com/gar3thjon3s/lein-expectations) Run [Expectations](https://github.com/jaycfields/expectations)-based tests
-   [lein-fixtures-sql](https://github.com/sc13-bioinf/lein-fixtures-sql) Generate sql fixtures from your db.
-   [lein-guzheng](http://github.com/dgrnbrg/lein-guzheng) Branch coverage analysis usable with any testing framefork
-   [lein-junit](https://github.com/febeling/lein-junit) Run JUnit tests
-   [lein-midje](https://github.com/marick/lein-midje) Run [Midje](http://github.com/marick/Midje/blob/master/README.md) tests
-   [lein-pjotest](https://github.com/jonpither/lein-pjotest) Run test namespaces in parallel with JUnit XML output
-   [lein-play](http://github.com/technomancy/lein-play) Play a different sound at the end of your test runs depending on whether they pass or fail
-   [lein-prism](https://github.com/aphyr/prism/) Auto-reload and rerun tests, works with vanilla clojure.test unlike the others mentioned here.
-   [lein-test-bang-bang](https://github.com/joegallo/lein-test-bang-bang) Run each test namespace in a separate JVM
-   [lein-test-from](https://github.com/joegallo/lein-test-from) Run your test namespaces, starting from a particular namespace
-   [lein-test-refresh](https://github.com/jakemcc/lein-test-refresh) Watch project for changes and automatically reload namespaces and run `clojure.test` tests.
-   [perforate](https://github.com/davidsantiago/perforate) Painless benchmarking with Leiningen and [Criterium](https://github.com/hugoduncan/criterium)
-   [quickie](https://github.com/jakepearson/quickie) Autotest clojure.test files.  Filters stacktraces to skip over some of the clojure cruft.
-   [speclj](https://github.com/slagyr/speclj) (pronounced “speckle”) TDD/BDD framework, with auto-runner, based on [rspec](http://rspec.info/)
-   [test2junit](https://github.com/ruedigergad/test2junit) Write test results to JUnit XML format suited for creating HTML reports. Allows automation of report generation as well.
-   [parallel-test](https://github.com/aredington/parallel-test) Run clojure.test tests in parallel with lein test style output. Supports fine grained configuration of what tests are executed in parallel, and how.

## Deployment

-   [jar-copier](https://carouselapps.com/jar-copier/) A Leiningen plugin to copy a jar from your dependencies into your resources.
-   [lein-aws](https://github.com/sorenmacbeth/lein-aws) A leiningen plugin to interact with Amazon Web Services
-   [lein-beanstalk](https://github.com/weavejester/lein-beanstalk) Deploy to AWS Elastic Beanstalk
-   [lein-bin](https://github.com/Raynes/lein-bin) Generate cross-platform standalone executables of your project
-   [lein-cloudbees](https://clojars.org/lein-cloudbees) Deploy clojure apps to cloudbees
-   [lein-cljs-lambda](https://github.com/nervous-systems/cljs-lambda) Template, plugin & library for deploying Clojurescript functions to AWS Lambda.
-   [lein-daemon](http://github.com/arohner/lein-daemon) Run app as a daemon
-   [lein-deploy-deps](https://github.com/neatonk/lein-deploy-deps) Deploy project dependencies to a remote repository
-   [lein-dist](http://github.com/pallet/lein-dist) Create a standalone tarball of your project source and dependencies
-   [lein-docker](https://github.com/sarnowski/lein-docker) Build and push Docker images
-   [lein-emr](https://github.com/dpetrovics/lein-emr) Create jobflows on Amazon Elastic MapReduce.
-   [lein-fpm](https://github.com/bts/lein-fpm) Build packages for multiple platforms (rpm, deb, etc.) using [fpm](https://github.com/jordansissel/fpm)
-   [lein-heroku-deploy](https://github.com/juggler/lein-heroku-deploy) Simplify your Heroku deploy
-   [lein-immutant](https://github.com/immutant/lein-immutant) Manage and deploy applications to an [Immutant](http://immutant.org) server
-   [lein-init-script](https://github.com/strongh/lein-init-script) Generate **NIX daemon scripts for your project
-   [lein-jelastic](https://github.com/mysema/lein-jelastic) Deploy to Jelastic
-   [lein-launch4j](https://github.com/RadicalZephyr/lein-launch4j) Wrap your project into a Windows `.exe` from any platform.
-   [lein-otf](https://github.com/timmc/lein-otf) Create non-AOT uberjars
-   [lein-package](https://github.com/pliant/lein-package) Allows for the packaging, installing, and deploying of artifacts besides jars, or multiple artifact projects.
-   [lein-ping](https://github.com/hashobject/lein-ping) Leiningen plugin that pings websites/urls. 
-   [lein-release](https://github.com/relaynetwork/lein-release) Bumps your version number and deploys
-   [lein-runit](https://github.com/danielsz/lein-runit) Integration with [runit](http://smarden.org/runit/), a UNIX init scheme with service supervision
-   [lein-runproject](https://github.com/weissjeffm/lein-runproject) Run any project's -main function directly from the repository
-   [lein-s3-static-deploy](https://github.com/ThoughtWorksInc/lein-s3-static-deploy) Deploy a local directory as a static website on s3
-   [lein-set-version](https://github.com/pallet/lein-set-version) Sets the version number in your project.clj
-   [lein-sha-version](https://github.com/pallet/lein-sha-version) Middleware to set the project version based on git SHA
-   [lein-sitemap](https://github.com/hashobject/lein-sitemap) Plugin for resubmitting sitemaps to Google Webmaster Tools. 
-   [lein-tar](http://github.com/technomancy/lein-tar) Create a tarball of your project and its dependencies, formerly lein-release
-   [lein-uberimage](http://github.com/palletops/lein-uberimage) Create a docker image with your project's uberjar
-   [lein-version-spec](https://github.com/circleci/lein-version-specs) Set the version number of your project according to rules
-   [lein-wagon-ssh-external](https://github.com/ToBeReplaced/lein-wagon-ssh-external) Use the apache wagon-ssh-external provider
-   [lein-worker](https://github.com/devth/lein-worker) Upload worker jars to IronWorker

## Web

-   [garden-watch](https://github.com/twashing/garden-watch) Watches for changes in your Garden (edn (CSS)) source files. 
-   [hiccup-watch](https://github.com/twashing/hiccup-watch) Watches for changes in your Hiccup (edn (HTML)) source files.
-   [lein-bower](https://github.com/wokier/lein-bower) Bower web lib dependency management 
-   [lein-gaeshi](https://github.com/slagyr/gaeshi) Google App Engine webs apps using Joodo. 
-   [lein-gwt-plugin](https://github.com/galdolber/gwt-plugin) Runs and compiles GWT applications
-   [lein-httpd](https://github.com/malyn/lein-httpd) Start a web server in the current directory. 
-   [lein-joodo](https://github.com/slagyr/joodo) Simple web app library.  Tasks to create, test, generate, your code.
-   [lein-karma](https://github.com/behrica/leiningen-karma-plugin) Runs JavaScript tests with Karma   
-   [lein-misaki](https://github.com/skuro/lein-misaki) Helps you building web sites using the [Misaki](https://liquidz.github.com/misaki/) static site generator
-   [lein-protractor](https://github.com/behrica/lein-protractor) Runs AngularJS e2e tests with Protractor 
-   [lein-ring](https://github.com/weavejester/lein-ring) Work with web applications using Ring
-   [lein-s3-static-deploy](https://github.com/ThoughtWorksInc/lein-s3-static-deploy) Deploy a local directory as a static website on s3
-   [lein-servlet](https://github.com/kumarshantanu/lein-servlet) Work with servlet-based webapps
-   [lein-simpleton](https://github.com/fogus/lein-simpleton) Serve files via http out of a local directory.
-   [touchme](https://github.com/sogilis/touchme) Touch files when html (by example) files are modified. Can be used to update enlive templates.
-   [lein-sitecompiler](https://github.com/dbushenko/lein-sitecompiler) The plugin allows generating a static website. Supports many template engines such as Mustache, Hiccup, Cuma, Fleet, Markdown.

## Databases

-   [clj-sql-up](https://github.com/ckuttruff/clj-sql-up) A simple plugin for running SQL database migrations
-   [datomic-schema-grapher](https://github.com/felixflores/datomic_schema_grapher) A library and lein plugin for graphing datomic schemas
-   [drift](http://github.com/macourtney/drift) Create and run Rails like database migrations in Clojure
-   [lein-dbmaintain](https://github.com/mysema/lein-dbmaintain) DbMaintain integration for Leiningen
-   [lein-dynamodb-local](https://github.com/dmcgillen/lein-dynamodb-local) Download and run an instance of DynamoDB Local
-   [lein-embongo](https://github.com/joelittlejohn/lein-embongo) Create a managed/embedded instance of MongoDB during a lein build (e.g. for integration testing).
-   [lein-flyway](https://github.com/metaphor/lein-flyway) - Flyway Migration Tool ported to Leiningen
-   [lein-ldapimem](https://github.com/mdaley/lein-ldapimem) - Create an embedded instance of unboundID's LDAP service (e.g. for testing) 
-   [lein-memcached](https://github.com/mdaley/lein-memcached) - Create an embedded instance of memcached (useful for testing)
-   [lein-postgres](https://github.com/whostolebenfrog/lein-postgres) Create an embedded instance of postgres for testing and development.
-   [lein-tern](http://github.com/bugsbio/lein-tern) - DB migrations as Clojure data.
-   [zookem](https://github.com/joelittlejohn/zookem) Create a embedded instance of Zookeeper during a lein build (e.g. for integration testing)

## Documentation

-   [cloc](https://github.com/jaley/cloc) Generate API docs for your project and dependencies and serve them through a local web server, with a fast Lucene full-text search.
-   [codox](https://github.com/weavejester/codox) A tool for generating API documentation from Clojure source code. (html)
-   [lein-asciidoctor](https://github.com/asciidoctor/asciidoctor-lein-plugin) Generate documentation using [Asciidoctor](http://asciidoctor.org)
-   [lein-clique](https://github.com/Hendekagon/lein-clique) Generate a graph of dependencies between the functions in your project
-   [lein-html5-docs](https://github.com/tsdh/lein-html5-docs) Generate HTML5 API docs
-   [lein-javadoc](https://github.com/davidsantiago/lein-javadoc) Automatically run javadoc on the java sources in your project
-   [lein-licenses](https://github.com/technomancy/lein-licenses) List licenses of all dependencies
-   [lein-margauto](https://github.com/tranchis/lein-margauto) Watches your source directories for changes to your clojure source files and rebuilds the Marginalia documentation whenever you update your source code
-   [lein-marginalia](https://github.com/fogus/lein-marginalia) Generate [Marginalia](https://github.com/fogus/marginalia) documentation
-   [lein-mustache](https://github.com/achin/lein-mustache) Evaluate Mustache templates with Clojure data files (e.g. for creating templatized documentation)
-   [lein-plantuml](https://github.com/vbauer/lein-plantuml) Generate UML diagrams using [PlantUML](http://plantuml.sourceforge.net)
-   [lein-precate](https://github.com/technomancy/lein-precate) Transform project.clj into Leiningen 2.x-compatible form.
-   [lein-sphinx](https://github.com/SnootyMonkey/lein-sphinx) Generate documentation from [reStructuredText](http://docutils.sourceforge.net/rst.html) using [Sphinx](http://sphinx-doc.org/).
-   [nephila](https://github.com/timmc/nephila) Show a graph of your Clojure namespaces
-   [gargamel](https://github.com/MailOnline/gargamel) generates pretty (with links etc) changelog based on git commit messages in multiple formats

## Deprecated

-   [fw1-template](https://github.com/seancorfield/fw1-template) Create [FW/1](https://github.com/seancorfield/fw1-clj) projects (use `lein new fw1 myapp` instead)
-   [lein-clojars](https://github.com/ato/lein-clojars) Deploy to Clojars (use `lein deploy clojars` instead)
-   [lein-heroku](https://github.com/technomancy/lein-heroku) Generate and manage Heroku apps (use [https://toolbelt.herokuapp.com](the toolbelt) instead)
-   [lein-idea](https://bitbucket.org/bkumar/lein-idea) Generates Intellij IDEA project files
-   [lein-midje-lazytest](https://github.com/myguidingstar/lein-midje-lazytest) Run Midje/Clojure tests on top of lazytest (Just a meta-package!)
-   [lein-noir](https://github.com/ibdknox/lein-noir) Create and manage [Noir](http://www.webnoir.org) projects (use `new` task)
-   [lein-outdated](https://github.com/ato/lein-outdated) List newer available versions of dependencies (use [lein-ancient](https://github.com/xsc/lein-ancient) instead)
-   [lein-swank](http://github.com/technomancy/swank-clojure) Launch a Swank server for Emacs integration (nrepl or ritz is recommended)

## Merged into Leiningen

-   [lein-javac](https://github.com/antoniogarrote/lein-javac) For compiling Java source (1.4+)
-   [lein-multi](http://github.com/maravillas/lein-multi) Run tasks against multiple dependency sets (such as multiple Clojure versions) at once (2.0+)
-   [lein-newnew](https://github.com/Raynes/lein-newnew) Next-generation `lein new` supporting custom project skeletons (2.0+)
-   [lein-plugin](http://github.com/trptcolin/lein-plugin) Manage plugins (1.4+)
-   [lein-retest](http://github.com/technomancy/lein-retest) Run only the test namespaces which failed last time around (1.6+)
-   [lein-run](http://github.com/sids/lein-run) Call -main functions from the command-line (1.4+)
-   [lein-search](http://github.com/Licenser/lein-search) Search remote repositories for artifacts (1.6+)