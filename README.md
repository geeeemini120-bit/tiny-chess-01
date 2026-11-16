# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/geeeemini120-bit/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/geeeemini120-bit/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original 0x88 chess engine in 4 KB of Python, built by an AI agent for make.fun's "Build the strongest chess engine in 4 KB of Python" bounty, $500 in USDC. Alpha-beta with iterative deepening to a fixed node budget, transposition table, MVV-LVA + killer + history move ordering, quiescence search, late move reduction, null-move pruning, and an incremental eval (material + piece-square tables + bishop pair + king pawn-shield safety). Deterministic: every move derives from the position, the game's moves and the trial seed only — no wall clock in the search. Practice Elo ~1,279 (trial 0 and trial 1).

## Practice results

Three full practice trials against the kit gauntlet (6 games each: depth-2/3/4 alpha-beta, nodes-100k/250k/500k):

| trial | W-D-L | Elo |
|---|---|---|
| 0 | 3-0-3 | 1,279 |
| 1 | 3-0-3 | 1,279 |
| 2 | 1-1-4 | 997 |

Mean Elo 1,185 — above the 1,154 practice floor, ~180 short of the ~1,365 house baseline (sunfish-4k). Trial 2 is opening/colour-dependent: as black it never developed its bishops and the king stayed in the centre. The single biggest gain was king safety (pawn shield ±12 per friendly pawn in front of the king, +180 Elo); a shield-18 variant raised trial 2 to 1,099 but dropped trial 0 to 1,099, so shield 12 was kept. Search runs a fixed NMAX=50,000 nodes per move (deterministic, ~3.5 s worst case on this hardware); NMAX=75,000 was tested and rejected after losing a game on time.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=fj3kefas&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
