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

# Code review

A reviewer is responsible to make sure that the PR adheres to our coding
standard before reviewing. The person committing is responsible to make sure it
adheres to the coding standard before creating the PR.

It is important to think of the tone in both comments from both parties. We are
all proud of what we do, but remember that we're all working towards the same
goal!

## Submitting a review

In general, the reviewer needs to weigh the effort of reviewing against how critical the
code is, and apply the more of steps if the code is more vital than if it is a less crucial part of the software.

#### To approve a code review, a reviewer _must_ make sure

##### That there is at least one test for every exported function

In Go this is everything starting with a capital letter, in Java this is
everything with visibility modifier `public`. - If it does not, list the functions that are not tested

##### That the reviewer ave a good understanding of the code

If some part is hard to get a good grip on, explain in the review what is confusing

#### To approve a code review, a reviewer _should_ point out

##### Any part of the code that took longer to read than others

For instance due to confusing variable names.

##### Further tests to increase coverage

A good ting to check is that all errors are returned as expected, and that all expected inputs do not return an error.

#### To approve a code review, a reviewer _may_ suggest:

##### Performance optimizations

It's always more important that code it is correct than that it is fast. Thus, performance improvements must never reduce maintainability and should not redice readability.

##### Refactoring to enable further testing, better maintainability or readability

Changes don't have to affect functionality, but can also just leave us with a more understandable and flexible codebase.

## Addressing a review

To address a code review, one can either straight away commit updates, or
propose to create an issue to fix in a subsequent PR.
