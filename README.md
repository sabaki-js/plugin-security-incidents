<img src="https://raw.githubusercontent.com/sabaki-js/sabaki/main/assets/logo.svg" width="120" alt="sabaki logo" />

# @sabaki-js/security-incidents

[![npm](https://img.shields.io/npm/v/%40sabaki-js%2Fsecurity-incidents)](https://www.npmjs.com/package/%40sabaki-js%2Fsecurity-incidents) [![license](https://img.shields.io/npm/l/%40sabaki-js%2Fsecurity-incidents)](https://github.com/sabaki-js/plugin-security-incidents#readme) [![CI](https://github.com/sabaki-js/plugin-security-incidents/actions/workflows/test-battery.yml/badge.svg)](https://github.com/sabaki-js/plugin-security-incidents/actions)

Security incident triage.

Questions: `true_positive` (0.77), `disposition` (0.73), `credential_compromise` (0.73), `severity` (0.63), `urgency` (0.57). Weights: 476 KB.

## Usage

```ts
import { Sabaki } from "sabaki";
import plugin from "@sabaki-js/security-incidents";

const sabaki = new Sabaki().register(plugin.default ?? plugin);
const r = sabaki.decide({ state: "..." });
// { domain: "security_incidents", decision: ..., confidence: ..., plugin: "@sabaki-js/security-incidents" }
```

Ask another question with `input.question`.

Part of [sabaki](https://github.com/sabaki-js/sabaki) - see the [GUIDE](https://github.com/sabaki-js/sabaki/blob/main/GUIDE.md).

## License

MIT
