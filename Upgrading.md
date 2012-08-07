# Upgrading

Interested in upgrading to Leiningen 2? I don't blame you! Look at
[all those great features](https://github.com/technomancy/leiningen/blob/master/NEWS.md).
Let me offer some tips for getting started.

## Installation

If you installed Leiningen 1.x by hand, move it out of the way first:

    $ mv ~/bin/lein ~/bin/lein1

Download
[`bin/lein`](https://raw.github.com/technomancy/leiningen/preview/bin/lein)
from the `preview` branch:

    $ wget -O ~/bin/lein https://raw.github.com/technomancy/leiningen/preview/bin/lein
    $ chmod 755 ~/bin/lein

Ensure `~/bin` is on your `$PATH`.

## Plugins

The most noticeable change in Leiningen 2 is that the way plugins work
has been totally revamped. It's much more reliable, but it might take
a bit of adjustment. Firstly, all your user-level plugins are now
stored in the `:user` profile instead of being manually installed. So
if you have the following:

    $ ls ~/.lein/plugins
    lein-difftest-1.3.8.jar  lein-marginalia-0.7.1.jar lein-swank-1.4.4.jar

You'll have to translate that into a `~/.lein/profiles.clj` file that
looks like this:

```clj
{:user {:plugins [[lein-difftest "1.3.8"]
                  [lein-marginalia "0.7.1"]
                  [lein-pprint "1.1.1"]
                  [lein-swank "1.4.4"] ]}}
```

This mechanism means that there is only ever one list of plugins, so
de-duplication issues between user-level plugins and project-level
plugins will never be a problem. It also means your configuration can
be checked into version control easily instead of having to re-run
`lein1 plugin install [...]` on every new machine on which you work.

For more details on the `:user` profile see `lein help profiles`.

You may run into issues since not all plugins out there have been
upgraded to work with Leiningen 2 yet. Please report such issues with
the plugin author and/or the Leiningen mailing list. If the
installation instructions for a plugin haven't been updated yet, you
can try replacing "lein plugin install [...]" with just adding the
corresponding name/version to the `:plugins` vector in your `:user`
profile. This won't work for all plugins since some of them rely on
violating the project/plugin isolation, but it will work for the
simpler ones.

## Precate

Now that your `:user` profile is in place, it's time to focus on the
project which you plan to upgrade. We'll install a plugin (using
Leiningen 1) to help with the process:

    $ lein1 plugin install lein-precate 0.3.1

Precate, of course, is the opposite of deprecate. Running `lein1
precate` in your project will show you a suggested configuration which
should be compatible with Leiningen 2, so it should just be a matter
of copying the output to `project.clj`. Of course, no automated
refactoring is perfect, so be sure to review it for a basic sanity
check. But it should cover the majority of cases.

## User-level Settings

The `~/.lein/init.clj` file is still loaded at Leiningen startup, but
it's no longer checked for settings. Most user-level settings should
be moved to the `:user` profile:

```clj
{:user {:plugins [[lein-difftest "1.3.8"]
                  [lein-marginalia "0.7.1"]
                  [lein-pprint "1.1.1"]
                  [lein-swank "1.4.4"]]
        :search-page-size 30
        :repl-options {:prompt (fn [ns] (str "your command, master? "))}}}
```

The exception is the `leiningen-auth` map, which should be copied and
encrypted in `~/.lein/credentials.clj.gpg`. See `lein help deploying`
under "Authentication" for details.

## Gotchas

Leiningen 2 uses jars straight from the local maven repository
(`~/.m2`), rather than also copying jars into the project's `lib`
directory as 1.x does.

While Leiningen 2's preview releases are very stable, it hasn't seen a
final 2.0.0 release since the current Clojars repository
[mingles snapshots with releases](https://github.com/ato/clojars-web/issues/24),
which is undesirable. Since switching the default repositories to a
releases-only Clojars (which is still in development) would be a
breaking change, a series of previews is being released in the mean
time.

You may find the
[lein-pprint](https://github.com/technomancy/leiningen/tree/master/lein-pprint)
plugin useful for debugging your project.

Please report any issues you run into to the
[mailing list](http://groups.google.com/group/leiningen) or the [#leiningen 
channel](irc://chat.freenode.net#leiningen) on Freenode.
