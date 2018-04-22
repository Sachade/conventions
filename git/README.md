# Git

## Good commit messages

Follow Erlang OTP's [commit message style
guide](https://github.com/erlang/otp/wiki/writing-good-commit-messages).

## Tests pass on every commit

Every commit is a self-contained change with an accompanying commit
message.

## Prefer rebasing to merging

Rebasing instead of merging keeps the git history as simple and linear as
possible.

If bugs are discovered, or changes are requested during code review, the
affected changes of the PR should be rewritten, as opposed to adding
fix-commits to the PR branch.

For example, commits with the heading _Fix review comments_ should be
avoided. Instead, rebase and rewrite the affected original commits.
