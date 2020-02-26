# Vue (Nuxt) project for testing [Sublime LSP bug #892](https://github.com/sublimelsp/LSP/issues/892)

## Requirements:
Sublime LSP and LSP-vue.

## One-time setup:
1. Run `npm i` to install dependencies.
2. Open this project in Sublime Text (restart ST if project was already open).

## Repro steps:
1. Open `pages/index.vue` and `utils/testing.ts` in the editor.
2. Verify that there are no typescript errors.
3. Open `types/index.d.ts` and change type of `Foo` to `number`.

## Expected:
Both `pages/index.vue` and `utils/testing.ts` should now show a typescript error.

## What happens:
Only `utils/testing.ts` shows an error. `pages/index.vue` still "sees" old "string" type.
Running `LSP: Restart servers` command fixes the issue.
