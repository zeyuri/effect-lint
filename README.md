# effect-lint

Oxlint JS plugin for Effect lint rules, implemented with Oxlint's alternative API for future performance gains.

This package ports the rules from `@codeforbreakfast/eslint-effect` and keeps the same rule names (prefix: `effect/`).

## Installation

```bash
npm install --save-dev @zeyuri/effect-lint oxlint
```

Or with Bun:

```bash
bun add -D @zeyuri/effect-lint oxlint
```

## Requirements

- `oxlint` >= 1.42.0
- JS plugins are experimental in Oxlint and may emit a warning on run

## Usage

`.oxlintrc.json`

```json
{
  "jsPlugins": ["@zeyuri/effect-lint"],
  "rules": {
    "effect/no-classes": "error",
    "effect/no-runSync": "error",
    "effect/no-runPromise": "error"
  }
}
```

## Config bundles

You can use the prebuilt configs in `configs/`:

- `configs/recommended.json`
- `configs/strict.json`
- `configs/no-gen.json`
- `configs/prefer-match.json`
- `configs/pipe-strict.json`

Example:

```bash
oxlint --config node_modules/@zeyuri/effect-lint/configs/recommended.json src
```

## Notes on the alternative API

All rules use `defineRule` and the plugin is wrapped with `definePlugin`. This is the Oxlint alternative API, which is designed to enable future performance improvements without changes to the rules.

## Development

```bash
bun install
bun run test
```

## Publishing

```bash
npm login
npm publish --access public
```
