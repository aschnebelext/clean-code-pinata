# Clean Code Pinata 🪅

## Description

This example Repository demonstrates how to use Prettier, ESLint, Husky &amp; Lint-Staged together to make code formatting a breeze experience.

All tools/packages above work great together and make sure, that your Repository always stays clean and formatted, before you even commit something.

## Prerequisite

If you like to play around with this Repository you need to install:

• Node Version 14.x or higher

## Why Pinata?

It's 8 PM in the evening and all my head was thinking about was a Pinata.

Use the following tools to

- keep your code-base clean by consisteny formatting
- enforce best practices & guidelines by statically code analyzes
- never ever think actively about the 2 points mentioned above

### [Prettier](https://prettier.io/)

Prettier is an opinionated code formatter which supports JavaScript, Typescript, and many Frameworks & Libraries.

Whenever you save your files, Prettier will make sure, that your code gets formatted.

It's dead simple.

But what if you not only want to format everything consistenly, but also enforce certain code guidelines?

### [ESLint](https://eslint.org/)

ESLint statically analyzes your code to find problems.

- Find Issues
- Fix problems automatically
- Easily extendable and configurable

Again, you can use it with almost every Language, Framework or Library.

If we could only make sure that 💩 doesn't slip into the code Repository...

### [Husky](https://typicode.github.io/husky/#/)

Husky lets you easily install and configure [Git Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks).

You can configure Husky for example to:

- Lint & format your code before you commit something
- Run tests to make sure everything runs smoothly
- What every comes to your mind

One downside could potentially be, that formatting and linting could take a while, because every file gets linted and formatted.

If there only would be one solution 🤔

### [Lint-Staged](https://github.com/okonet/lint-staged)

Use Lint-Staged together with husky to only lint/format what has been changed.

## Install & Setup

### Prettier

First, install Prettier locally:

```shell
npm install --save-dev --save-exact prettier
```

Then create a config file:

```shell
echo {}> .prettierrs.json
```

Use basic configuration (or extend/update the configuration [using the available options](https://prettier.io/docs/en/options.html):

```json
{
  "trailingComma": "es5",
  "tabWidth": 4,
  "semi": false,
  "singleQuote": true
}
```

Next create a `.prettierignore`(https://prettier.io/docs/en/ignore.html) file to ignore certain files and folders completely from formatting.

By default prettier ignores files in version control systems directories (".git", ".svn" and ".hg") and node_modules (if --with-node-modules CLI option not specified).

You can test Prettier now by running:

```shell
npx prettier --write .
```

### ESLint

Install ESLint & configure locally.

```shell
npm init @eslint/config
```

A wizzard will guide your through the installation process.

Note: Use "To check syntax, find problems, and enforce code style" only, when your code base is either fairly new or already consistent and clean.
Otherwise you will probably face a ton or errors and need to fix them which could take a while.

This example Repository uses the 2nd option.
The configuration can either be a JavaScript File, YAML or JSON. I choose JavaScript.
For further configuration details checkout [Configuring ESLint](https://eslint.org/docs/latest/user-guide/configuring/).

You can try out ESLint by running:

```shell
npx eslint .
```

Note: If you're using Prettier with ESLint together we need to make further adjustments.

### Prettier X ESLint

To get Prettier work well together with ESLint we need to install additional plugins:

```shell
npm install --save-dev eslint-config-prettier eslint-plugin-prettier
```

Next we need to adjust the `.eslintrc.js` (if you choosen YAML, or JSON, use the respective file and adjust it accordingly):

```JavaScript
// .eslintrc.js
module.exports = {
    "env": {
        "browser": true,
        "es2021": true
    },
    "plugins": ["prettier"], // new
    "extends": [ // Extends is an array now
        "eslint:recommended",
        "plugin:prettier/recommended" // new
    ],
    "overrides": [
    ],
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    },
    "rules": {
        "prettier/prettier": "error" // new
    }
}
```

Now both—ESlint & Prettier should work together hand in hand.
