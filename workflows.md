# Workflows

There are lots of ways one might get a co-authored-by trailer into a git commit
message. Some are more manual than others, let's document some:

## When authoring the commit message

A commit message is typically authored either with a `-m` flag or using your
$EDITOR. In either case, one could copy/paste the trailer, maybe something like:

```
$ git commit -m "We did this and that\n\n$(pear curret:trailer)"
```

## After making a commit

Sometimes its easier to add the trailer afterwards:

```
$ git commit -m "We did this and that"
$ pear amend
```

## Before the commit

If you want to get the trailer in there before the commit even happens, you have
a few options:

### prepare-commit-msg hook

This hook fires with a few args that help massage the commit message. Since it's
a hook, it would have to be configured in each git repo.

### commit template

One can specify a file as their git commit template and it will be used each
time a commit is about to be authored.

---

If you don't have strong feelings about how this should work or just want a
solid suggestion, here's what I think you should do:

Edit your `~/.gitconfig` to include a `hooksPath` if you haven't already done
so. Point it at a folder of your choosing and then do this:

```shell
# assuming your `hooksPath` is `~/.git-hooks`
$ pear hooks:add prepare-commit-msg ~/.git-hooks
```

The `pear hooks:add` command takes a hook type and a path. It outputs a script
for that hook type at the path. It also ensures that file is executable.

With this in place, all one would have to do to get the Co-authored-by trailer
in their commit message would be this:

```shell
$ pear current:add orta
$ git commit
```

Your editor should open with something like this:

```

Co-authored-by: Orta Therox <orta.therox@gmail.com>
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
# ...etc...
```

So then you can add your message and tweak things as you'd like and save.
