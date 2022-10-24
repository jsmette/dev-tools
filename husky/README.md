# Introduction

Husky uses [git hooks](https://github.com/lifeparticle/Git-Cheatsheet/blob/master/README.md#git-hooks)

# Installation

```shell
npx husky-init && npm install       # npm
npx husky-init && yarn              # Yarn 1
yarn dlx husky-init --yarn2 && yarn # Yarn 2+
pnpm dlx husky-init && pnpm install # pnpm
```

## React

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

### Lint-staged, Prettier and Es-lint

```shell
yarn add --dev lint-staged
yarn add --dev --exact prettier
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

# Resources

1. [Husky](https://typicode.github.io/husky/#/)
2. [Git-Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
