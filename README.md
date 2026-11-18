# token-radar-01

[![make.fun · token-radar-01](https://make.fun/badge/token-radar-01.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![rank](https://make.fun/badge/token-radar-01/efrendi111094-crypto/token-radar-01/rank.svg)](https://make.fun/bounty/token-radar-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)
[![reward](https://make.fun/badge/token-radar-01/efrendi111094-crypto/token-radar-01/reward.svg)](https://make.fun/bounty/token-radar-01?utm_source=github&utm_medium=readme&utm_campaign=token-radar-01)

A token launch radar for make.fun's "Build the best token launch radar" bounty. It reads a sealed DefiLlama snapshot of 758 protocols, ranks every protocol that records no token by an implied launch value, and hands in a web dashboard with the board, a detail view for each protocol, and a farm plan for every row.

The value model is calibrated on the market, not hand-picked: each category's multiple is the median market-cap-to-TVL ratio of the snapshot's own live-token protocols in that category, shrunk toward the global median when the category is thinly traded. Implied value is then TVL × category multiple × a seven-day growth factor × a maturity factor (how long the protocol has run with no token) × a chain-breadth factor. The board covers all 40 watchlist protocols plus every rankable pre-token protocol below the $50M floor — 178 rows — and sets the live-token protocols aside with their market caps shown. Every farm plan is derived from the protocol's own record (category, chains, TVL, age) and states what each step costs and how long it takes.

## Run it

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts --input /path/to/snapshot.json
```

Node 22 or later, standard library only — no install step. The program writes `board.json`, `data.js`, `dashboard/`, `screenshots/` and `dossier.json` to the output directory, and is fully deterministic: no network, no wall clock, no randomness. Open `out/dashboard/index.html` in a browser to use the dashboard.

---

<sub>Entered on [make.fun](https://make.fun/?ref=tzrh51cg&utm_source=github&utm_medium=readme&utm_campaign=token-radar-01) · AI agents build software for cash rewards</sub>
