---
name: tpcw-quant
description: Parent router for Atlas long-term portfolio research and Bayes mid/short trading-bot research. Use when the user says tpcw-quant, /tpcw-quant, or Use tpcw-quant. Not for engineering (poteto-mode), literature (/deep-research), or live trading.
disable-model-invocation: true
license: MIT
---

# tpcw-quant

Meta skill for shop quant research. One parent for Atlas and Bayes. Launch `grok --always-approve -p "Use tpcw-quant. <ticket: goal, constraints, done-check>."`

Category playbooks live in this plugin at `vendor/llmquant-skills` (pinned [LLMQuant/skills](https://github.com/LLMQuant/skills) submodule). They are files this parent opens. They are not first-class slash commands.

If `vendor/llmquant-skills/skills` is missing, stop. Tell the operator to run `git submodule update --init` in the tpcw-quant checkout and reinstall the plugin. Do not fetch workflow text from the network as a substitute.

## Bounce first

Match the *deliverable*, not the topic.

| Deliverable | Do this |
|---|---|
| Code in a repo (impl, PR, tests, millie `decide()`, harness changes) | Stop. Tell them to rerun with poteto-mode. |
| Literature / vendor / harness investigation | Stop. Tell them to rerun with `/deep-research`. |
| Live trading, orders, signing, deploying capital, "just send it" | Refuse. No live without an explicit OK on the ticket. |
| Quant research memo, thesis, watchlist, regime, edge kill, event brief | Stay. |

millie *code* is poteto-mode. millie-specific research workflow is not in this plugin yet. Do not invent one. For "is this millie edge real / how do we kill it" use `quant.md` below and the millie checkout as data.

## Hat

Pick one hat for this turn. Say it. Do not start a second parent.

- **Atlas**: long-term book. Income-ETF core, QQQ, satellites. Thesis, watchlist, profile, ETF overlap, research hygiene. Not an execution bot.
- **Bayes**: mid/short bots. Crypto regime/token/funding, prediction-market briefs and arb *research*, systematic edge kill. Quant capital is separate from the Atlas book.

If the ask spans both, pick the hat that owns the decision this turn.

## Pick one file

Open **one** workflow. Read it in full. Follow it. Do not load sibling workflows in the same category.

Paths are relative to this plugin root (parent of `skills/`).

### Atlas

| Ask | File |
|---|---|
| Company research profile | `vendor/llmquant-skills/skills/llmquant-portfolio/workflows/company-profile.md` |
| Thesis with sell conditions | `vendor/llmquant-skills/skills/llmquant-portfolio/workflows/investment-thesis-tracker.md` |
| Theme basket | `vendor/llmquant-skills/skills/llmquant-portfolio/workflows/theme-research.md` |
| Watchlist monitor | `vendor/llmquant-skills/skills/llmquant-portfolio/workflows/watchlist-monitor.md` |
| ETF overlap / concentration | `vendor/llmquant-skills/skills/llmquant-etfs/workflows/etf-overlap-report.md` |
| Research quality / overfitting / isolation | `vendor/llmquant-skills/skills/llmquant-risk/workflows/research-health-check.md` |

### Bayes

| Ask | File |
|---|---|
| Crypto market regime | `vendor/llmquant-skills/skills/llmquant-crypto/workflows/crypto-market-regime.md` |
| Token or protocol memo | `vendor/llmquant-skills/skills/llmquant-crypto/workflows/crypto-token-research.md` |
| Perp funding, basis, OI, leverage crowding | `vendor/llmquant-skills/skills/llmquant-crypto/workflows/crypto-perp-funding-monitor.md` |
| Event probability brief | `vendor/llmquant-skills/skills/llmquant-prediction-markets/workflows/event-probability-brief.md` |
| Cross-venue prediction-market arb *research* | `vendor/llmquant-skills/skills/llmquant-prediction-markets/workflows/prediction-market-arb-watch.md` |
| Implied prob vs options | `vendor/llmquant-skills/skills/llmquant-prediction-markets/workflows/probability-vs-options-pricing.md` |
| Is this edge real / how do we kill it | `vendor/llmquant-skills/skills/llmquant-strategies/workflows/quant.md` |

### Unlisted

The tables are the tested set, not a wall. If the ask clearly matches another file under `vendor/llmquant-skills/skills/*/workflows/*.md`, open that one file and label the reply **unlisted leaf**. Do not invent a millie workflow this way. Do not treat `alert-manager` as permission to stand up a watcher or go live.

## Data

Do not require LLMQuant Data MCP. v1 uses millie tape, SiYuan, user-provided numbers, and pages you can actually fetch.

Harvested workflows tell you to prefer LLMQuant Data. Ignore that requirement. Keep their isolation, hypothesis-before-data, and "label the gap" rules.

- Separate retrieved facts from interpretation.
- Name the source and the as-of date.
- If funding, TVL, holdings, fills, or a tape is missing, say so and stop that claim. Do not invent it.

## Live

Research only. Perp funding and arb watch are read-and-report. No orders, no keys, no signing, no "paper that is actually live."
