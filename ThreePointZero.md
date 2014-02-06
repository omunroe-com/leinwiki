Version 3.0 is an opportunity to make a number of changes that we've
been unable to so far due to backwards-compatibility.

Below the larger issues are discussed.

## Profile Merging

The fact that you can't do ad-hoc `assoc` or `update-in` modifications
to the project map followed by a profile merge is a pretty big cause
of confusion and headaches for many. In addition, the rules for
conflict resolution
[don't always make sense](https://github.com/technomancy/leiningen/issues/878).

## Monkeypatching in the test task

The `test` task includes a number of monkeypatches to the
`clojure.test` library due to the fact that it's nearly impossible to
get patches accepted upstream. However, it's become a textbook example
of tasks that do way too much and would be much better served by a
library. Virtually everything in the test task should be moved to an
external library that is specified as a :dependency of the
project. (We should add a `:dependencies` entry in the `lein new`
templates as well as possibly an `:aliases` entry for `test`.) Apart
from being cleaner, this makes Leiningen less opinionated about what
testing library you should use. We may build upon the
[conjecture](https://github.com/pjstadig/conjecture) library.

## Specifying :filespecs for jar inclusion

This is a mess; we should start from scratch.

## Profile isolation

Profiles are great for enabling certain functionality under a given
context. Ideally the effects of a given profile are active only for a
certain execution of a given task, but if the profile ends up writing
artifacts to disk (most commonly with AOT compilation), you can end up
with cross-profile contamination since all profiles share the same
`:target-path` values. In Leiningen 2.3.0 we introduced support for
isolating `:target-path` on a per-profile basis. However, some people
had workflows which assumed a hard-coded target path, causing
breakage, so it's currently an opt-in feature until 3.0.

## Implicit AOT

During the development of 2.0, we removed the implicit AOT that
happens when you specify a `:main` namespace. However, it was
accidentally reintroduced, and went unnoticed until after 2.0.0 was
released. 3.0 will allow us to get rid of it again.

## Java class support in run task

This complicates things a lot and is very rarely used; it should move
to a plugin.

## Custom Unquote

We implement our own unquote with `~` in `defproject`. Now that
read-eval is a documented feature of Clojure, we should deprecate our
implementation and refer folks to that instead.

## Utils namespace

A few defns need to be moved around to avoid cyclic dependencies.
