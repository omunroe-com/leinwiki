# Project Middleware

There has been some discussion in [#leiningen](http://lazybot.org/logs/#leiningen/2011-11-16) and on the [mailing list](http://groups.google.com/group/leiningen/browse_thread/thread/4b7cd2a998637ce8) about allowing plugins to modify the defproject map. This basically makes plugins middleware for the project.

### Why is this useful?

* Plugins could use this to add things like repositories or deployment information to a project.
* This would allow profiles/environments/contexts to be written as a plugin.
* A company could spin-out common project.clj boilerplate into their own plugin to share among multiple projects.
* This would make it easy for task dependencies (like those provided by cake's `deftask`) to be specified inside defproject. We could provide helper functions for plugins to add task dependencies to the project map.

### What would this look like in practice?

* Each plugin defines a function that will be called on the project map sequentially in the order plugins were required.
  * Classpath ordering seems like the way to go for determining precedence
* One way to support this would be to require plugins to be named `lein-*` and define their project middleware wrapper in `leiningen.plugins.*`.
* Another option is to put some info in the jar `META-INF/MANIFEST.MF`.