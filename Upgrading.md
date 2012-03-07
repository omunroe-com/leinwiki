# Upgrading

Interested in upgrading to Leiningen 2? I don't blame you! Look at
[all those great features](https://github.com/technomancy/leiningen/blob/master/NEWS.md).
Let me offer some tips for getting started.

## Installation

Download
[`bin/lein`](https://raw.github.com/technomancy/leiningen/preview/bin/lein)
from the `preview` branch:

    $ wget -O ~/bin/lein2 https://raw.github.com/technomancy/leiningen/preview/bin/lein
    $ chmod 755 ~/bin/lein2

This is assuming you have `~/bin` on your `$PATH`. You probably want
to place the `lein2` symlink wherever your existing Leiningen 1
installation is. At some point you'll probably want to just name it
`lein`, but for now let's play it safe and leave the old 1.x version
around.

## Plugins

The most noticeable change in Leiningen 2 is that the way plugins work
has been totally revamped. It's much more reliable, but it might take
a bit of adjustment. Firstly, all your user-level plugins are now
stored in the `:user` profile instead of being manually installed. So
if you have the following:

    $ ls ~/.lein/plugins
    lein-difftest-1.3.7.jar  lein-marginalia-0.7.0.jar lein-swank-1.4.3.jar

You'll have to translate that into a `~/.lein/profiles.clj` file that
looks like this:

```clj
{:user {:plugins [[lein-difftest "1.3.7"]
                  [lein-marginalia "0.7.0"]
                  [lein-pprint "1.0.0"]
                  [lein-swank "1.4.3"]]}}
```

This mechanism means that there is only ever one list of plugins, so
de-duplication issues between user-level plugins and project-level
plugins will never be a problem. It also means your configuration can
be checked into version control easily instead of having to re-run
`lein plugin install [...]` on every new machine on which you work.

You may run into issues since not all plugins out there have been
upgraded to work with Leiningen 2 yet. Please report such issues with
the plugin author and/or the Leiningen mailing list.

## Precate

Now that your `:user` profile is in place, it's time to focus on the
project which you plan to upgrade. We'll install a plugin (using
Leiningen 1) to help with the process:

    $ lein plugin install lein-precate 0.2.0

Precate, of course, is the opposite of deprecate. Running `lein
precate` in your project will show you a suggested configuration which
should be compatible with Leiningen 2, so it should just be a matter
of copying the output to `project.clj`. Of course, no automated
refactoring is perfect, but this should cover the majority of cases.

## User-level Settings

The `~/.lein/init.clj` file is still loaded at Leiningen startup, but
it's no longer checked for settings. Most user-level settings should
be copied to the `:user` profile. The exception is the
`leiningen-auth` map, which should be copied to the `:auth` profile in
`~/.lein/profiles.clj`:

```clj
{:user {:plugins [[lein-difftest "1.3.7"]
                  [lein-marginalia "0.7.0"]
                  [lein-pprint "1.0.0"]
                  [lein-swank "1.4.3"]]
        :search-page-size 30}
 :auth {:repository-auth {#"http://blueant.com/archiva/"
                           {:username "milgrim"
                            :password "locative.2"}}}}
```

## Gotchas

While Leiningen 2 is fairly stable, it's not quite ready for a release
candidate yet; there are still a few features missing. In particular
if you need shell wrappers or the ability to selectively clean
`.class` files after compilation, you may want to stick with version 1
for a little longer. 

You may find the
[lein-pprint](https://github.com/technomancy/leiningen/tree/master/lein-pprint)
plugin useful for debugging your project.

Please report any issues you run into to the
[mailing list](http://groups.google.com/group/leiningen) or the [#leiningen 
channel](irc://chat.freenode.net#leiningen) on Freenode.
