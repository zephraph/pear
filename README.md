# pear [![CircleCI][badge]][circleci]

Credit where credit is due.

## Workflows

Pear can be used in any number of ways, but they basically boil down to these:

* copy/paste trailer into commit message
* amend commit with trailer
* automate trailer with post commit hook

The first two are more manual in case git hooks aren't your thing while the last
helps automate.

## Cutting a new release

The process of cutting a new release is mostly managed by CircleCI. All that
needs to be done locally is running the release script:

```
# those args are old/new version numbers
$ ./bin/release 0.0.0 0.0.1
```

This script will find the old version, replace with the new version and then do
all the git things to get GitHub updated and kick off the release job on Circle.

<!-- toc -->
* [Usage](#usage)
* [Commands](#commands)
<!-- tocstop -->
# Usage
<!-- usage -->
```sh-session
$ npm install -g @jonallured/pear
$ pear COMMAND
running command...
$ pear (-v|--version|version)
@jonallured/pear/0.2.0 darwin-x64 node-v10.15.1
$ pear --help [COMMAND]
USAGE
  $ pear COMMAND
...
```
<!-- usagestop -->
# Commands
<!-- commands -->
* [`pear amend`](#pear-amend)
* [`pear current`](#pear-current)
* [`pear current:add`](#pear-currentadd)
* [`pear current:clear`](#pear-currentclear)
* [`pear current:trailer`](#pear-currenttrailer)
* [`pear help [COMMAND]`](#pear-help-command)
* [`pear init`](#pear-init)
* [`pear known`](#pear-known)
* [`pear known:add`](#pear-knownadd)

## `pear amend`

amend last commit message with trailers

```
USAGE
  $ pear amend
```

_See code: [src/commands/amend.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/amend.ts)_

## `pear current`

list current authors

```
USAGE
  $ pear current
```

_See code: [src/commands/current/index.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/current/index.ts)_

## `pear current:add`

add current author

```
USAGE
  $ pear current:add
```

_See code: [src/commands/current/add.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/current/add.ts)_

## `pear current:clear`

clear current authors

```
USAGE
  $ pear current:clear
```

_See code: [src/commands/current/clear.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/current/clear.ts)_

## `pear current:trailer`

list current authors in trailer format

```
USAGE
  $ pear current:trailer
```

_See code: [src/commands/current/trailer.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/current/trailer.ts)_

## `pear help [COMMAND]`

display help for pear

```
USAGE
  $ pear help [COMMAND]

ARGUMENTS
  COMMAND  command to show help for

OPTIONS
  --all  see all commands in CLI
```

_See code: [@oclif/plugin-help](https://github.com/oclif/plugin-help/blob/v2.1.4/src/commands/help.ts)_

## `pear init`

create the ~/.pear-data file

```
USAGE
  $ pear init
```

_See code: [src/commands/init.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/init.ts)_

## `pear known`

list known authors

```
USAGE
  $ pear known
```

_See code: [src/commands/known/index.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/known/index.ts)_

## `pear known:add`

add known author

```
USAGE
  $ pear known:add
```

_See code: [src/commands/known/add.ts](https://github.com/jonallured/pear/blob/v0.2.0/src/commands/known/add.ts)_
<!-- commandsstop -->

[badge]: https://circleci.com/gh/jonallured/pear.svg?style=svg
[circleci]: https://circleci.com/gh/jonallured/pear
