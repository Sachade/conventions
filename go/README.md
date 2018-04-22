# Go

## Formatter

Format with `goimports`.

## Linter

Lint with [gometalinter][gometalinter].

Fix all reported issues before submitting a PR.

* [ ] **TODO:** Define which specific linters to enable

## Style guide

Follow the following style and best practice guides in descending order of
importance:

* [Effective go](https://golang.org/doc/effective_go.html)
* [Code review comments](https://github.com/golang/go/wiki/codereviewcomments)
* [Go best practices, six years in](http://peter.bourgon.org/go-best-practices-2016/)
* [Go best practices for production environments](http://peter.bourgon.org/go-in-production/)

## Naming conventions

Follow [Andrew Gerrand's naming
conventions](https://talks.golang.org/2014/names.slide).

The naming conventions favor short names, but also:

* Think about context
* Use your judgment

Remember to optimize for readability and ease of understanding. Do not
optimize for brevity.

## Directory layout

**TODO:** Decide if to adopt [Ben Johnson's standard package
layout](https://medium.com/@benbjohnson/standard-package-layout-7cdbc8391fc1).

## Additions

### Max 100 characters per line

The `gofmt` tool does not enforce line length.

For readability's sake, especially for GitHub code reviews, we aim to keep
our lines below 100 characters.

### Avoid package-level globals

Global variables lead to code that is harder to reason about, harder to
test, and it makes an API implicitly non-thread safe.

More context:

* [Theory of modern Go](https://peter.bourgon.org/blog/2017/06/09/theory-of-modern-go.html)
* [Go without package-scoped variables](https://dave.cheney.net/2017/06/11/go-without-package-scoped-variables)

> Why are package scoped variables bad? Putting aside the problem of
> globally visible mutable state in a heavily concurrent language, package
> scoped variables are fundamentally singletons, used to smuggle state
> between unrelated concerns, encourage tight coupling and makes the code
> that relies on them hard to test.

[gometalinter]: https://github.com/alecthomas/gometalinter
[effective-go]: https://golang.org/doc/effective_go.html
[naming-conventions]: https://talks.golang.org/2014/names.slide#1
