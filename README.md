# pear

Credit where credit is due.

I was just reading the docs on topics and wanted to brainstorm another way pear
could be used:

```
$ pear init
# => create the ~/.pear-authors file

$ pear known
# => list the known authors from ~/.pear-authors

$ pear known:add foo
# => add an entry for foo to the ~/.pear-authors file

$ pear known:remove foo
# => remove an entry for foo from the ~/.pear-authors file

$ pear known:add-org foo
# => add all users from GitHub org foo to the ~/.pear-authors file

$ pear known:remove-org foo
# => remove all users from GitHub org foo from the ~/.pear-authors file

$ pear coauthors
# => spits back the current list of coauthors from the ./.pear file

$ pear coauthors:add foo
# => adds foo to the ./.pear file

$ pear coauthors:set foo
# => sets foo as the only coauthors in the ./.pear file

$ pear coauthors:clear
# => removes the ./.pear file

$ pear hook
# => check for hook

$ pear hook:add
# => add the post-commit hook

$ pear hook:clear
# => removes the post-commit hook

$ pear hook:run
# => the command run when post-commit triggers
```



[![CircleCI](https://circleci.com/gh/jonallured/pear/tree/master.svg?style=shield)](https://circleci.com/gh/jonallured/pear/tree/master)

<!-- toc -->
* [pear](#pear)
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
@jonallured/pear/0.0.1 darwin-x64 node-v11.3.0
$ pear --help [COMMAND]
USAGE
  $ pear COMMAND
...
```
<!-- usagestop -->
# Commands
<!-- commands -->
* [`pear add`](#pear-add)
* [`pear clear`](#pear-clear)
* [`pear help [COMMAND]`](#pear-help-command)
* [`pear init`](#pear-init)
* [`pear post-commit`](#pear-post-commit)

## `pear add`

add author to .pear file

```
USAGE
  $ pear add
```

_See code: [src/commands/add.ts](https://github.com/jonallured/pear/blob/v0.0.1/src/commands/add.ts)_

## `pear clear`

clear current .pear file

```
USAGE
  $ pear clear
```

_See code: [src/commands/clear.ts](https://github.com/jonallured/pear/blob/v0.0.1/src/commands/clear.ts)_

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

create the ~/.pear-authors file

```
USAGE
  $ pear init
```

_See code: [src/commands/init.ts](https://github.com/jonallured/pear/blob/v0.0.1/src/commands/init.ts)_

## `pear post-commit`

git hook to amend commit with authors

```
USAGE
  $ pear post-commit
```

_See code: [src/commands/post-commit.ts](https://github.com/jonallured/pear/blob/v0.0.1/src/commands/post-commit.ts)_
<!-- commandsstop -->
