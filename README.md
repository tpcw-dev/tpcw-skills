# tpcw-quant

Thin **parent skill** for [Grok Build](https://github.com/xai-org) (`grok -p`): a poteto-mode analog that bundles quant playbooks and routes Atlas (long-term portfolio research) and Bayes (mid/short trading bots) to the right sub-skill.

Public home for the skill. Shop process: SiYuan `Guide/_index` (working copy: Grok Bot skill `grok-build`) and Quant ticket **quant-38**.

## Status

Not implemented yet. quant-37 researched the starting point (2026-09-02):

- Write a thin in-house parent `SKILL.md` (pstack match-then-load).
- Harvest [LLMQuant/skills](https://github.com/LLMQuant/skills) workflow files as leaf raw material.
- Do **not** adopt [LLMQuant/quant-mind](https://github.com/LLMQuant/quant-mind) as the runtime or clone it onto the Grok Bot computer.
- Launch remains `grok -p` from the project cwd. Not a standing Grok Bot chat skill.

Grill + build: Quant ticket **quant-38**.

## Launch

Skill name and repo name are both **tpcw-quant**.

Two generic leaves (grilling on quant-38):

- `portfolio-management` — Atlas. Maps LLMQuant portfolio (thesis / watchlist / digest).
- `quant-dev` — Bayes. Holds crypto and prediction-market skills.

```bash
grok --always-approve -p "Use tpcw-quant. <ticket: goal, constraints, done-check>."
```

Flags before `-p`. Code tickets still use **poteto-mode**. Literature tickets still use **/deep-research**. This parent is for Atlas/Bayes *quant* tasks.

## What this is not

- Not Lauren Tan’s pstack / `poteto-mode` (engineering playbooks).
- Not a live trading bot. No live without an explicit OK.
- Quant capital is separate from the long-term book.
- Not [hani-q/qstack](https://github.com/hani-q/qstack).

## License

MIT
