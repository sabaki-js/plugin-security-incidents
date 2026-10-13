# @sabaki-js/security-incidents

Typed decisions over security incidents (triage, severity, disposition).

A [sabaki](https://github.com/sabaki-js/sabaki) plugin. Router keywords included:
register it and `Sabaki.decide()` routes matching states here automatically.

## Install

```sh
npm install @sabaki-js/security-incidents sabaki
```

Zero runtime dependencies (bundled TF-IDF weights, 476 Ko).

## Usage

```ts
import { Sabaki } from "sabaki";
import mail from "@sabaki-js/security-incidents";

const sabaki = new Sabaki();
sabaki.register(mail.default ?? mail);
const r = sabaki.decide({ state: "Votre facture mobile est disponible", question: "disposition" });
// { domain: "security_incidents", decision: ..., confidence: ..., plugin: "@sabaki-js/security-incidents" }
```

Ask another question with `input.question` (any of the list below).


## Questions (measured on held-out test sets)

- `true_positive` — accuracy **0.770** (true/false)
- `disposition` — accuracy **0.730** (classes)
- `credential_compromise` — accuracy **0.730** (true/false)
- `severity` — accuracy **0.630** (levels)
- `urgency` — accuracy **0.570** (levels)

Accuracies are honest test-split numbers, not marketing. See `sabaki` for the
`nano` / `mini` modes and the benchmark methodology.

## License

MIT
