# Conventions

Conventions for how we build quality software.

## Why

Having common conventions enables us to produce higher quality software
faster.

Conventions increase the number of issues caught before [code
review](./code-review), so that reviewers can focus on what matters (in
order of importance):

* Correctness
* Ease of understanding
* Efficiency

Conventions ensure that our code looks the same no matter who writes it.
This makes it faster and easier for us to ramp up in new parts of the code
base.

## What

For every language we build software in, we strive to have at least:

* A formatter, to remove all formatting discussions from code review
* A linter, to catch common errors before code review
* A style guide, to further increase uniformity of our code

## How

We strive to make it effortless to follow our conventions.

This means we prefer the **default configuration** for formatters and
linters, and we rely on **industry-standard style guides** instead of
writing our own from scratch.

When there are conflicts between formatters, linters and style guides, the
formatter prevails over the linter, which prevails over the style guide.

We strive to use automation and tooling to support our conventions where
it makes sense. Before adding automation, a judgement call should be made
with respect to required time investment and added maintenance overhead to
our build pipelines.

## Adding or updating conventions

See [CONTRIBUTING.md](./CONTRIBUTING.md).
