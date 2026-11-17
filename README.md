# knip-repro-canvaskit-wasm

Regression: `knip --strict` reports `canvaskit-wasm` as an unused dependency in knip 6.45.0 and later. In 6.44.2 it does not.

```sh
npm install
npm run knip                     # knip 6.45.1: Unused dependencies (1) canvaskit-wasm
npm i -D knip@6.44.2 && npm run knip   # no issues
```

`astro-og-canvas` is imported in `src/index.ts`, which enables the astro-og-canvas plugin. That plugin lists `canvaskit-wasm` as an optional dependency.
