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
yarn create react-app react-husky --template typescript
npx husky-init && yarn
```

The abvoe commands should generate the following code inside the `package.json` file:

```json
{
  "scripts": {
    "prepare": "husky install"
  }
}
```

# Resources

1. [Husky](https://typicode.github.io/husky/#/)
2. [Git-Hooks](https://git-scm.com/book/en/v2/Customizing-Git-Git-Hooks)
