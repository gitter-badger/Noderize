---
id: scripts
title: Noderize Scripts
sidebar_label: Scripts
---

Noderize comes build it with commands ("scripts"). These scripts are automatically added to your `package.json` `scripts` field when using [`create-noderize`](create.md):

```json
"scripts": {
    "watch": "noderize-scripts watch",
    "build": "noderize-scripts build",
    "start": "noderize-scripts start",
    "format": "noderize-scripts format",
    "test": "noderize-scripts test"
}
```

These scripts depend on `@noderize/scripts`.

You can run Noderize's command like so:

```bash
yarn <script>
# or
npm run <script>
```

> Note: with npm, you may omit `run` for the `start` and `test` scripts. For example: `npm start`.

For every the `watch` and `start` script, you may pass arguments to both Noderize and your app:

```bash
yarn watch [noderize args] -- [app args]
# or
npm run watch [noderize args] -- [app args]
```

If only passing arguments to your app (and not Noderize), you must add a double `--`:

```bash
yarn watch -- -- [app args]
# or
npm run watch -- -- [app args]
```

## Index

<AUTOGENERATED_TABLE_OF_CONTENTS>

## Scripts

### `build`

Builds your apps.

Uses [build options](configuration-noderize.md#build-options).

### `start`

Runs your built app.

Uses [run options](configuration-noderize.md#run-options).

### `watch`

Continuously builds are runs your app.

Uses [build](configuration-noderize.md#build-options) & [run options](configuration-noderize.md#run-options).

### `format`

[Format](features-formatting.md) all of your code.

Uses [Prettier options](configuration-prettier.md).

You can pass options directory to Prettier:

```bash
yarn format --useTabs
# or
npm run format --useTabs
```

### `test`

Runs your [tests](features-testing.md).

Uses [Jest options](configuration-jest.md).

You can pass arguments directly to Jest:

```bash
yarn test --ci
# or
npm test --ci
```

> Note: To use Noderize's build options (such as [`babel`](configuration-noderize.md#babel) and [`languages`](configuration-noderize.md#languages)), you must set them to file configs.

### `clean`

Cleans your output directory (`dist`). Useful before publishing.
