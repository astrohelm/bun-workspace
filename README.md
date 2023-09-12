<h1 align="center">Astrohelm Bun workspace</h1>

<h2 align="center">Installation guide 🚀</h2>

### First step: workspace installation

Use next commands to install and update your workspace Or use this repository as a template
repository.

```bash
  # Download repository
  git clone https://github.com/astrohelm/bun-workspace ./path/to/workspace
  rm -rf ./path/to/workspace/.git ./path/to/workspace/package-lock.json
  cd ./path/to/workspace
  # Update and install dependencies
  ncu -u
  bun install
  # Update Bun.js (optional()
  bun upgrade
```

### Second step: Package personalization

Update package json, all with prefix <code>your-</code><br/> If your nodejs version newer than
package.json current add <code>|| your-node-version</code>.

```js
// package.json
{
  "license": "MIT",
  "version": "0.0.1",
  "type": "module",
  "name": "your-package-name",
  "homepage": "https://astrohelm.ru",
  "description": "your-package-description",
  "author": "your-name <your-mail>",
  "keywords": ["your-keyword #1", "your-keyword #n"],

  "main": "index.ts",
  "module": "index.ts",
  "readmeFilename": "README.md",
  "files": ["/lib", "/types"],

  "scripts": {
    "test": "bun test",
    "dev": "bun ./index.ts",
    "prettier:fix": "prettier --write \"**/*.{js,ts,json,html,cjs,md,yaml}\"",
    "eslint:fix": "eslint --fix \"**/*.{js,ts}\""
  },

  "repository": { "type": "git", "url": "git+https://github.com/astrohelm/your-package-name.git" },
  "bugs": { "url": "https://github.com/astrohelm/your-package-name/issues", "email": "your-mail" },

  "devDependencies": {
    "bun-types": "latest",,
    "@types/node": "^18.15.10",
    "eslint": "^8.40.0",
    "eslint-config-astrohelm": "^1.0.0",
    "eslint-config-prettier": "^8.8.0",
    "eslint-plugin-import": "^2.27.5",
    "eslint-plugin-prettier": "^4.2.1",
    "prettier": "^2.8.8",
  },
  "peerDependencies": {
    "typescript": "^5.0.0"
  }
}
```

### Third step: About files

Go to CHANGELOG.md and update it for your package. _WARNING !_ Don't fotget about date (xxxx-xx-xx).

```md
<!-- CHANGELOG.md -->

# Changelog

## [Unreleased][unreleased]

## [0.0.1][] - xxxx-xx-xx

- Stable release version
- Repository created

[unreleased]: https://github.com/astrohelm/your-package-name/compare/release...HEAD
[0.0.1]: https://github.com/astrohelm/your-package-name/releases/tag/release
```

Update AUTHORS

```md
 <!-- AUTHORS -->

your-name <your-mail>
```

### Almost last step: Update README.md

Replace your README.md with next information and change Your-package-name to actual.

```md
<h1 align="center">Your-package-name v0.0.1</h1>

<h2 align="center">Initial release 🚀</h2>

<h2 align="center">Copyright & contributors</h2>

<p align="center">
Copyright © 2023 <a href="https://github.com/astrohelm/Your-package-name/graphs/contributors">Astrohelm contributors</a>.
Workspace is <a href="./LICENSE">MIT licensed</a>.<br/>
Workspace is part of <a href="https://github.com/astrohelm">Astrohelm ecosystem</a>.
</p>
```

### Last step: Save results

_WARNING !_ Update this file before moving throw this step.

Create a new package in [organization][https://github.com/astrohelm/] repository. Use next commands
to save you package.

```bash
git init
git remote add origin your-package-location
git branch -M main # if your default branch is not main
git commit -am "Repository init"
git tag v0.0.1
git push origin main
git push origin v0.0.1
git checkout -b dev
git push origin dev
```

Return to your organization repository and do:

- Add keywords
- Update description
- Draft release with `release` tag and `v0.0.1` as a title and updated README file as description.

> If you creating library you may publish it now to npm with `npm publish` command.

Congratulations, package initialized 🚀

## About files & structure

This workspace have commonjs in use by default. You can switch it in package.json if you want.

- `dist` directory used for fronted package analog. You can use it if your package is multi-platform
  based.
- `eslint` astrohelm eslint rules
- `types` .d.ts library types exports
- `CHANGELOG.md` in use for project history documentation
- `Makefile` ultimate commands shortcuts creator
- `tests` here you can put all test coverage of your package
- `.github` github ci pipeline by default
- `lib` folder should contain all you library logic, _WARNING !_ Remove if you not writing library.
  Replace with src folder.

<h2 align="center">Copyright & contributors</h2>

<p align="center">
Copyright © 2023 <a href="https://github.com/astrohelm/bun-workspace/graphs/contributors">Astrohelm contributors</a>.
This workspace is <a href="./LICENSE">MIT licensed</a>.<br/>
And it is part of <a href="https://github.com/astrohelm">Astrohelm ecosystem</a>.
</p>
