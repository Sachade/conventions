# Python

## Formatter

Format with [Google's yapf](https://github.com/google/yapf) using the
default settings.

## Linter

Lint with [flake8](http://flake8.pycqa.org/en/latest/) using the default
settings.

Fix all reported issues before submitting a PR.

There should be no conflicts with yapf (since we use the default PEP8
settings for both). If there are conflicts, yapf wins.

## Style guide

Look to [Google's Python Style
Guide](https://google.github.io/styleguide/pyguide.html).

## Additions

### Use Python 3

Use `#!/usr/bin/env python3` unless a vital dependency is only available
for Python 2.

Avoid writing and maintaining our own libraries in Python 2 to the
furthest extent possible.
