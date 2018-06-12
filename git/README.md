# Git

## Formatter

When using Markdown in commit messages, format with the designated
[markdown formatter](../markdown/README.md#formatter).

## Linter

Lint your commit messages with `gitlint` using the default config.

**Note:** This linter requires every commit message to have a body. A body
may be redundant for some commits, but the time spent on adding a minimum
of context to every commit leads to faster reviews and faster ramp-up of
new developers.

To use this linter as a commit hook, run `gitlint install-hook` once in
every repository where you want it enabled.

```
git commit --amend
gitlint: checking commit message...
6: B2 Line has trailing whitespace: "A line with trailing whitespace!  "
-----------------------------------------------
gitlint: Your commit message contains the above violations.
Continue with commit anyways (this keeps the current commit message)? [y(es)/n(no)/e(dit)]
```

## Style guide

Follow Erlang OTP's [commit message style
guide](https://github.com/erlang/otp/wiki/writing-good-commit-messages).

Most importantly, use imperative mode in the summary:

> Write the summary line and description of what you have done in the
> imperative mode, that is as if you were commanding someone. Start the
> line with "Fix", "Add", "Change" instead of "Fixed", "Added", "Changed".

## Additions

### Configure your git's line ending behavior

Line endings are different for different operating systems. In order to
ensure a smooth collaboration across plattforms, your git should be set
according to [this article here](https://stackoverflow.com/questions/10418975/how-to-change-line-ending-settings).
For further reading, please refer to [here](https://stackoverflow.com/questions/3206843/how-line-ending-conversions-work-with-git-core-autocrlf-between-different-operat) and [here](http://web.archive.org/web/20150912185006/http://adaptivepatchwork.com:80/2012/03/01/mind-the-end-of-your-line/).

### Tests pass on every commit

Every commit is a self-contained change with an accompanying commit
message.

### Prefer rebasing to merging

Rebasing instead of merging keeps the git history as simple and linear as
possible.

If bugs are discovered, or changes are requested during code review, the
affected changes of the PR should be rewritten, as opposed to adding
fix-commits to the PR branch.

For example, commits with the heading _Fix review comments_ should be
avoided. Instead, rebase and rewrite the affected original commits.
