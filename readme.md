# Babel (v7.18+) Tape Runner v1.0.0

A simple test runner for Tape with modern Babel support for ESNext features. Forked from [Wavded's Babel Tape Runner](https://github.com/wavded/babel-tape-runner).

## Installation

### Set your GITHUB_TOKEN environment variable

To install this (and any other GitHub) packages, you'll first need to set the **GITHUB_TOKEN** environment variable.
To do this you'll first need to create a GitHub Token (classic), you can do so on the "Developer options" section of your GitHub settings page.
For more instructions, read [GitHub's documentation](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic).

Once set, add your access token to your preferred terminal's user profile file.

On Windows, WindowsPowerShell is recommended, locate or create your user profile file, usually saved on **%USERPROFILE%/Documents/WindowsPowerShell/Microsoft.Powershell_profile.ps1**, and add this line:

```powershell
$Env:GITHUB_TOKEN="<Your Token>"
```

On MacOS, locate or create your default terminal's user profile file.

For **bash** terminals it can be found at **~/.bashrc**
For **zsh** terminals it can be found at **~/.zshrc**

Then add this line:

```bash
export GITHUB_TOKEN="<Your Token>"
```

### Install the package

Now you can run either:

```bash
npm install --save @ittidigital/eslint-config-muv
```

or

```bash
yarn add -D @ittidigital/eslint-config-muv
```

### Resolve to GitHub Package Registry

Locate or create your NPM configuration file, usually saved on **./.npmrc** , it should contain the following:

```npmrc
registry=https://registry.npmjs.org/ # or https://registry.yarnpkg.com/
@hersy:registry=https://npm.pkg.github.com/
//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}
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

Just run `npx babel-tape-runner` with the files to test (just like tape's bundled runner). Store configuration in a `.babelrc` file.

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
