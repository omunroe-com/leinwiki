Leiningen is a tool designed around project automation. But without
repeatability, automation is worthless.

You can think of a build as a function of the current state of the
project and the repositories referenced by the project's
configuration. The return value is the output, exit code, and artifact
files produced.

Anything that increases the chance of the build behaving differently
on different machines is repeatability poison and should be
eliminated. Here are a few of the most common offenders.

TODO: explain

## Free-floating Jars

## User-level Repositories

## Snapshot Versions

## Version Ranges

## Testing
