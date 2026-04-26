# stainless-config

Stainless SDK generation config for [vaif-studio](https://github.com/vaifllc/vaif-studio).

## What's in here

- `stainless.yml` — main Stainless config, mapping OpenAPI operations from `https://api.vaif.studio/openapi.json` to SDK resource methods.

## How to update

1. The OpenAPI spec lives at `apps/api/openapi.json` in the [vaif-studio repo](https://github.com/vaifllc/vaif-studio).
2. Regenerate with: `pnpm exec tsx scripts/codemod/generate-stainless-config.ts` (in vaif-studio).
3. Copy the produced `stainless.yml` to this repo, commit, push.
4. Stainless picks up changes on its next polling cycle (or trigger manually in the dashboard).

## SDK targets

- `vaif-tech/vaif-js` — TypeScript SDK
- `vaif-tech/vaif-python` — Python SDK
- `vaif-tech/vaif-swift` — Swift SDK

Per-language config tuning may live in `.stainless/<lang>.yml` files (TBD as we tune output).
