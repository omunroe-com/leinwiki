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
