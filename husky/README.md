# Introduction

Husky uses [git hooks](https://github.com/lifeparticle/Git-Cheatsheet/blob/master/README.md#git-hooks)

# Installation

```shell
npx husky-init && npm install       # npm
npx husky-init && yarn              # Yarn 1
yarn dlx husky-init --yarn2 && yarn # Yarn 2+
pnpm dlx husky-init && pnpm install # pnpm
```

## React, Husky, Lint-staged, Es-lint, and Prettier

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

`package.json`

```json 
"lint-staged": {
  "*.{js,ts,tsx}": "eslint --fix"
}
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

```shell
yarn add --dev --exact prettier
```

```shell
yarn add --dev eslint-config-prettier
```

# Resources

1. [Husky](https://typicode.github.io/husky/#/)
2. [Git-Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
