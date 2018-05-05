# JavaScript

## Formatter

Format with [prettier](https://prettier.io/) using the default settings.

## Linter

Lint with [ESLint](https://eslint.org) with the following
`.eslintrc.json`:

```json
{
  "extends": ["airbnb", "prettier"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error"
  }
}
```

Bootstrap a new project using:

```
npm install --save-dev \
  eslint \
  eslint-config-airbnb \
  eslint-config-prettier \
  eslint-plugin-import \
  eslint-plugin-jsx-a11y \
  eslint-plugin-prettier \
  eslint-plugin-react \
  prettier
```

Fix all reported issues before submitting a PR.

## Style guide

Look to [Airbnb's JavaScript Style Guide](https://github.com/airbnb/javascript).
