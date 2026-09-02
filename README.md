# tpcw-quant

Thin **parent skill** for [Grok Build](https://github.com/xai-org) (`grok -p`): a poteto-mode analog that bundles quant playbooks and routes Atlas (long-term portfolio research) and Bayes (mid/short trading bots) to the right sub-skill.

Public home for the skill. Shop process: SiYuan `Guide/_index` (working copy: Grok Bot skill `grok-build`) and Quant ticket **quant-38**.

## Credits

Category skills and workflows come from **[LLMQuant/skills](https://github.com/LLMQuant/skills)** (MIT). We submodule that catalog; we do not claim authorship of those playbooks.

> Copyright (c) 2026 LLMQuant and contributors

See their [LICENSE](https://github.com/LLMQuant/skills/blob/master/LICENSE). The parent `SKILL.md` in this repo (when-to-use-what routing for Grok Build) is ours.

## Status

Not implemented yet. Grill is on Quant ticket **quant-38**.

- Thin in-house parent `SKILL.md` (guide: which hat, then which `llmquant-*` category).
- Reference [LLMQuant/skills](https://github.com/LLMQuant/skills) via git submodule (pin a commit; not a port).
- Do **not** adopt [LLMQuant/quant-mind](https://github.com/LLMQuant/quant-mind) as the runtime.
- Launch remains `grok -p` from the project cwd. Not a standing Grok Bot chat skill.

## Launch

Skill name and repo name are both **tpcw-quant**.

```bash
grok --always-approve -p "Use tpcw-quant. <ticket: goal, constraints, done-check>."
```

Flags before `-p`. Code tickets still use **poteto-mode**. Literature tickets still use **/deep-research**. This parent is for Atlas/Bayes *quant* tasks.

## What this is not

- Not Lauren Tan's pstack / `poteto-mode` (engineering playbooks).
- Not a live trading bot. No live without an explicit OK.
- Quant capital is separate from the long-term book.
- Not [hani-q/qstack](https://github.com/hani-q/qstack).
- Not LLMQuant Data (hosted API). v1 runs skills with their missing-data fallback.

## License

This repository's parent skill and docs: MIT.

The vendored [LLMQuant/skills](https://github.com/LLMQuant/skills) catalog: MIT, Copyright (c) 2026 LLMQuant and contributors. Their copyright notice and permission notice are included with the submodule.
