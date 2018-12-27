# @vikr01/renovate-config

My [shareable config](https://renovatebot.com/docs/config-presets/) for [Renovate](https://renovatebot.com).

[![npm version](https://img.shields.io/npm/v/@vikr01/renovate-config.svg)](https://npmjs.org/package/@vikr01/renovate-config)
[![npm downloads per month](https://img.shields.io/npm/dm/@vikr01/renovate-config.svg)](https://npmjs.org/package/@vikr01/renovate-config)
[![Travis Build Status](https://img.shields.io/travis/com/vikr01/renovate-config.svg?logo=travis)](https://travis-ci.com/vikr01/renovate-config)
[![Dependency Status](https://img.shields.io/david/vikr01/renovate-config.svg?label=dependencies)](https://david-dm.org/vikr01/renovate-config)
[![DevDependency Status](https://img.shields.io/david/dev/vikr01/renovate-config.svg?label=devDependencies)](https://david-dm.org/vikr01/renovate-config?type=dev)

## Setup

Just add this package directly to your `renovate.json` (or [other renovate config variations](https://github.com/renovatebot/renovate/blob/master/docs/configuration.md#configuration-methods)).

For [the latest version from `npm`](https://npmjs.org/package/@vikr01/renovate-config):

```json
{
  "extends": ["@vikr01"]
}
```

To use [this repository's config](./renovate.json):

```json
{
  "extends": ["github>vikr01/renovate-config"]
}
```

## Presets

### `@vikr01` (default)

- Bumps `dependencies` and `devDependencies` whenever a new version is published.
  - For example, `^3.0.0` will be bumped to `^3.0.1` even though `3.0.1` the still fits the range of `^3.0.0`. This is to prevent lockfiles from preventing useful dependency updates.
- Separates major and minor patches of dependencies
  - For example, updates for `eslint-plugin-import` from `^2.14.0` to `^2.15.0` and `prettier` from `^1.0.0` to `^2.0.0` will be separated into different pull requests.
- Groups ESLint, Prettier, and Stylelint dependencies together under the name `linters`
- Disables updating `engines` in `package.json` files.
- Renovate updates occur only between `6:00 AM` and `5:00 PM` PST on saturdays
