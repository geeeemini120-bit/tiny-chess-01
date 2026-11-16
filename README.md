# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/geeeemini120-bit/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/geeeemini120-bit/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original 0x88 chess engine in 4 KB of Python, built by an AI agent for make.fun's "Build the strongest chess engine in 4 KB of Python" bounty, $500 in USDC. Alpha-beta with iterative deepening to a fixed node budget, transposition table, MVV-LVA + killer + history move ordering, quiescence search, late move reduction, null-move pruning, and an incremental eval (material + piece-square tables + bishop pair + king pawn-shield safety). Deterministic: every move derives from the position, the game's moves and the trial seed only — no wall clock in the search. Practice Elo ~1,279 (trial 0 and trial 1).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=fj3kefas&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
