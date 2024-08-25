# Babel (v7.18+) Tape Runner v1.0.0

A simple test runner for Tape with modern Babel support for ESNext features. Forked from [Wavded's Babel Tape Runner](https://github.com/wavded/babel-tape-runner).

## Installation

### Resolve to GitHub Package Registry

Locate or create your NPM configuration file, usually saved on **./.npmrc** , and add this line:

```npmrc
@hersy:registry=https://npm.pkg.github.com/
```

### Install Package

#### To install the package to your project, run:

```bash
npm install --save @hersy/babel-tape-runner
```
or
```bash
yarn add -D @hersy/babel-tape-runner
```

#### To install it globally, run:

```bash
npm install -g --save @hersy/babel-tape-runner
```
or
```bash
yarn global add -D @hersy/babel-tape-runner
```

### Resolve Previous Package Name

If you want your dependencies to import this version of `babel-tape-runner` instead of the previous ones on NPM, you can configure your `package.json` to force update the package.

#### For npm managed packages, add this line to your `overrides` field:

```json
  "overrides": {
    "babel-tape-runner": "@hersy/babel-tape-runner@^1.0.0"
  },
```

#### For yarn managed packages, add this line to your `resolutions` field:

```json
  "resolutions": {
    "babel-tape-runner": "@hersy/babel-tape-runner@^1.0.0"
  },
```

And you're all set!

## Usage

Just run `babel-tape-runner` with the files to test (just like tape's bundled runner). Store configuration in a `.babelrc` file.

```sh
babel-tape-runner my-es-next-test.js
babel-tape-runner lib/**/__tests__/*-test.js # or glob patterns
```

For example, use this in your `package.json` file so you can run `npm test` or '`yarn test` to execute your tests:

```json
{
  "scripts": {
    "test": "babel-tape-runner \"lib/**/__tests__/*-test.js\" | faucet"
  },
}
```
