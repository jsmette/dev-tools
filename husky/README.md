# Introduction

Husky uses [git hooks](https://github.com/lifeparticle/Git-Cheatsheet/blob/master/README.md#git-hooks)

# Installation

```shell
npx husky-init && npm install       # npm
npx husky-init && yarn              # Yarn 1
yarn dlx husky-init --yarn2 && yarn # Yarn 2+
pnpm dlx husky-init && pnpm install # pnpm
```

[Source](https://typicode.github.io/husky/#/)

## React, Husky, Lint-staged, Es-lint, Prettier, and Eslint-config-prettier

```shell
# create a react app called react-husky with typescript
yarn create react-app react-husky --template typescript
```

```shell
# create a folder called .husky with pre-commit hook script
npx husky-init && yarn
```

The abvoe commands should generate the following code inside the `package.json` file:

`package.json`

```json
{
  "scripts": {
    "prepare": "husky install"
  }
}
```

```shell
yarn add --dev lint-staged
```

`.husky\pre-commit`

```
#!/usr/bin/env sh
. "$(dirname -- "$0")/_/husky.sh"

npx lint-staged
```

```shell
yarn add --dev eslint
npx eslint --init
```

```shell
Need to install the following packages:
  @eslint/create-config
Ok to proceed? (y) y
√ How would you like to use ESLint? · style # To check syntax, find problems, and enforce code style       
√ What type of modules does your project use? · esm # JavaScript modules (import/export)
√ Which framework does your project use? · react # React
√ Does your project use TypeScript? · No / Yes # Yes
√ Where does your code run? · browser # Browser
√ How would you like to define a style for your project? · guide # Use a popular style guide
√ Which style guide do you want to follow? · standard-with-typescript # Standard: https://github.com/standard/eslint-config-standard-with-typescript
√ What format do you want your config file to be in? · JSON # JSON
Checking peerDependencies of eslint-config-standard-with-typescript@latest
The config that you've selected requires the following dependencies:
```

Remove the following code block from `package.json` file.

```json
"eslintConfig": {
  "extends": [
    "react-app",
    "react-app/jest"
  ]
},
```

Add the following code block inside the `package.json` file to automatically fix problems.

```json 
"lint-staged": {
  "*.{js,ts,tsx}": "eslint --fix"
}
```

[Source](https://eslint.org/docs/latest/user-guide/getting-started)

```shell
yarn add --dev --exact prettier
```

[Source](https://prettier.io/docs/en/index.html)

Turns off all rules that are unnecessary or might conflict with Prettier.

```shell
yarn add --dev eslint-config-prettier
```

 Add `prettier` to the `extends` array inside the .eslintrc.* file. Make sure to put it last, so it gets the chance to override other configs.
 
 ```json
{
  "extends": [
    "some-other-config-you-use",
    "prettier"
  ]
}
```

[Source](https://github.com/prettier/eslint-config-prettier)

# Resources

1. 
