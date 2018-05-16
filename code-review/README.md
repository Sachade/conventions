# Code review

## Before submitting PR

Make sure your code follows the conventions set out in this repository for
all the relevant languages in your PR.

This includes always following our [git](../git) conventions in how your
commits are structured and how your commit messages are phrased.

Make sure the code is correctly formatted by the right tool and that you
have fixed all linter warnings.

## When reviewing a PR

First, be constructive.

Second, remember our values:

* Correctness
* Ease of understanding
* Efficiency

Be as specific as possible when requesting changes. Propose alternate
solutions and provide example code snippets to explain what you mean.

Be mindful of the tone of your comments. We are all proud of what we do,
we own our code together, and we are working toward the same goal.

Use your judgement when requesting changes. Code reviews are about
achieving sustainable speed over time, but we also need to move fast and
ship often.

Done is better than perfect, but we must never compromise on safety.

### Review checklist

#### The reviewers _must_ request changes to ensure

* [ ] There is at least one test for every exported function

In Go this is everything starting with a capital letter, in Java this is
everything with visibility modifier `public`. Request at least one test
for every exported function.

* [ ] The code is comprehensible

When you can't understand the code well enough to know that it is correct,
provide suggestions for how the code can be simplified.

#### The reviewers _should_ propose changes changes to ensure

* [ ] The code is easy to read and understand

Provide suggestions on how to further improve readability. For example;
help the author simplify the control flow and find better variable names.

* [ ] The code has good test coverage

Suggest additional tests to verify that error cases behaves as expected,
and that no valid input leads to an error.

When applicable, provide suggestions for how [property-based
testing](https://en.wikipedia.org/wiki/QuickCheck) can be used.

#### The reviewers _may_ suggest changes to encourage

* [ ] The code is performant enough for the context in which it runs

Benefits from any performance optimization must always be greater than the
added cost of reduced maintainability and readability.

Correct code beats fast code, but we should help each other avoid
[premature pessimization](https://herbsutter.com/2013/05/13/gotw-2-solution-temporary-objects/).

> Premature pessimization is when you write code that is slower than it
> needs to be, usually by asking for unnecessary extra work, when
> equivalently complex code would be faster and should just naturally flow
> out of your fingers.
>
> -- Herb Sutter

* [ ] Refactorings to improve testability, maintainability or readability

Always be on the lookout for ways to make our code base simpler and more
understandable, without impacting features and functionality.
