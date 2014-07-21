# Deploying Signatures to Existing Clojars Artifacts

It's great to get in the habit of signing your jars as you deploy
them. However, you may have already deployed old versions of your
library before you got in the habit of signing. If this is the case,
don't fret! It's easy to sign your existing artifacts and deploy the
signatures back to Clojars.

Unfortunately there's a bug in Leiningen that's just been fixed on
master, so if you try this with 2.4.2 or older it will try to deploy
`mylib-1.3.asc`, which is the wrong thing.

First get the artifacts. They're most likely already in your
`~/.m2/repository` directory, but there is a chance the local copy may
not match the remote copy exactly, so it's best to delete these first
and force them to be re-fetched. Create a dummy project that depends
on the artifacts you want to sign and run `lein deps :verify` to force
them to get pulled in. Before you sign them, you should open up the
jar file and pom file to confirm that their contents are
correct. Signing artifacts you have not confirmed that you trust
defeats the whole purpose of the signature. If the jar file contains
.class files, then it's basically impossible to inspect, and you
should not sign it.

What you don't want to do is simply re-generate the jar files and pom
files from your checkout and deploy those signatures, because the
timestamps of the newly-generated versions will differ from the
deployed artifacts, and your signatures will not match the artifacts
on Clojars.

If they check out, copy them from `~/.m2/repository` into your project
directory and sign them:

```
$ cp ~/.m2/repository/mylib/mylib/1.3.1/mylib-1.3.1.{jar,pom} .
$ gpg -ab mylib-1.3.1.jar
$ gpg -ab mylib-1.3.1.pom
```

Next deploy the signatures:

```
$ lein deploy clojars mylib 1.3.1 mylib-1.3.1.jar.asc mylib-1.3.1.pom.asc
```

That should do the trick. Switch to the dummy project that depends on
your library and run `lein deps :verify` again to confirm that the
signatures are picked up correctly.
