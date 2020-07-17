---
templateKey: blog-post
title: How to find a git branch and check it out in one command
date: 2020-07-16T22:00:00.000Z
description: >-
  A one-liner function to find a branch by a keyword and checkout the result in
  git. Should be added to your aliases.
featuredpost: false
featuredimage: /img/screenshot-2020-07-17-at-12.16.19.png
tags:
  - git
  - automation
---
I switch branches in my projects **a lot**. What I'm always struggling with, though, is remembering branch names.

In my team, branch naming convention is `[feature/bugfix]/<ticketNumber>-<description-in-snake-case>` which makes it hard to guess branch name if you're in a hurry.

I wrote a shortcut command to help with those cases. Here it is in my `.zshrc`:

```
function gbco() {
        git checkout $(git branch | grep -i "$1")
}
```

`gbco` is short for `git branch checkout` (not a real command, just easy for me to remember).

### How it works

We're doing a `git checkout` command and pass the result of whatever is in `$()` as a parameter.

In the parentheses, we list all the branches of a current repo using `git branch`, and then pass that output into a `grep` command to search within. `-i` flag will make sure that search is case-insensitive, and `"$1"` is there to pass the first argument after `gbco` command.

### Usage
I'm looking for a branch that has a word `project` in the name.

```
$ gbco project                                                                                                                                
Switched to branch 'feature/us261565-labs-project-id'
Your branch is up to date with 'origin/feature/us261565-labs-project-id'.
```

### Corner cases
This function does not cover cases when more than 1 branch contains a keyword for your search, or when no branches are found. I might think of handling those cases later.
