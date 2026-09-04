# tpcw-skills

Former GitHub/plugin name: **tpcw-quant** (repo redirected).

Thin **parent skill** for [Grok Build](https://github.com/xai-org) (`grok -p`): a poteto-mode analog that bundles quant playbooks and routes Atlas (long-term portfolio research) and Bayes (mid/short trading bots) to the right sub-skill.

Public home for the skill. Shop process: SiYuan `Guide/_index` (working copy: Grok Bot skill `grok-build`) and Quant ticket **quant-38**.

## Credits

Category skills and workflows come from **[LLMQuant/skills](https://github.com/LLMQuant/skills)** (MIT). We submodule that catalog; we do not claim authorship of those playbooks.

> Copyright (c) 2026 LLMQuant and contributors

See their [LICENSE](https://github.com/LLMQuant/skills/blob/master/LICENSE). The parent `SKILL.md` in this repo (when-to-use-what routing for Grok Build) is ours.

## Status

v1 locked 2026-09-03 (quant-38 grill). Parent `skills/tpcw-skills/SKILL.md` is a Grok plugin. Catalog is a pinned git submodule at `vendor/llmquant-skills`.

- Thin in-house parent `SKILL.md` (hat, then one `llmquant-*` workflow file).
- Reference [LLMQuant/skills](https://github.com/LLMQuant/skills) via git submodule (pin a commit; not a port).
- Do **not** adopt [LLMQuant/quant-mind](https://github.com/LLMQuant/quant-mind) as the runtime.
- Launch remains `grok -p` from the project cwd. Not a standing Grok Bot chat skill.
- No LLMQuant Data MCP in v1. Missing-data fallback. millie-specific workflow is a later leaf.

## Install

Grok's plugin clone may not fetch submodules. Install from a checkout that already has the catalog.

```bash
git clone --recurse-submodules https://github.com/tpcw-dev/tpcw-skills.git
cd tpcw-skills
git submodule update --init --recursive
grok plugin install "$(pwd)" --trust
```

Enable it next to pstack in `~/.grok/config.toml`:

```toml
[plugins]
enabled = ["pstack", "tpcw-skills"]
```

`grok plugin list` should show `tpcw-skills`. `grok inspect` should list skill `tpcw-skills` from the plugin. `/llmquant-crypto` and the other catalog folders must **not** appear as slash commands.

## Launch

Skill name and repo name are both **tpcw-skills** (formerly tpcw-quant). Explicit invoke only.

```bash
grok --always-approve -p "Use tpcw-skills. <ticket: goal, constraints, done-check>."
```

Flags before `-p`. Code tickets still use **poteto-mode**. Literature tickets still use **/deep-research**. This parent is for Atlas/Bayes *quant* research.

## What this is not

- Not Lauren Tan's pstack / `poteto-mode` (engineering playbooks).
- Not a live trading bot. No live without an explicit OK.
- Quant capital is separate from the long-term book.
- Not [hani-q/qstack](https://github.com/hani-q/qstack).
- Not LLMQuant Data (hosted API). v1 runs skills with their missing-data fallback.

## License

This repository's parent skill and docs: MIT.

The vendored [LLMQuant/skills](https://github.com/LLMQuant/skills) catalog: MIT, Copyright (c) 2026 LLMQuant and contributors. Their copyright notice and permission notice are included with the submodule.
