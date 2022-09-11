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











