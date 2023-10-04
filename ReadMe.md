# vite-zustand-config-issue

This repository demonstrates a configuration issue encountered when building a project using Vite and Zustand. The issue arises when executing the build command `npm run build`, and results in a TypeScript error regarding interface extension within Zustand's `devtools.d.ts`.

https://github.com/pmndrs/zustand/issues/2101

## Reproduction Steps

1. Clone this repository.
2. Install dependencies with `npm install`.
3. Run the build command with `npm run build`.

You should encounter the following TypeScript error:

```bash
> vite-zustand-config-issue@0.0.0 build
> tsc && vite build

node_modules/zustand/esm/middleware/devtools.d.ts:33:42 - error TS2312: An interface can only extend an object type or intersection of object types with statically known members.

33 export interface DevtoolsOptions extends Config {
                                            ~~~~~~

Found 1 error in node_modules/zustand/esm/middleware/devtools.d.ts:33
```

## Description

The error above is thrown during the build process, pointing towards an issue with the `DevtoolsOptions` interface extending `Config` within `devtools.d.ts` file of the Zustand library.

## Environment

- Vite version: `^1.0.0-rc.13`
- Zustand version: fails on `4.4.2`, works on `4.4.1`
- TypeScript version: `4.1.2`
- Node version: `v18.18.0`
- npm version: `9.8.1`

## License

[MIT](./LICENSE.md)
