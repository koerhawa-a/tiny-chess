# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/koerhawa-a/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/koerhawa-a/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python: 0x88 board, negamax alpha-beta with quiescence, transposition table, killer and history ordering, null-move pruning, LMR, and a tapered piece-square evaluation. It searches to a fixed node budget per move, never to a clock, so every game replays deterministically. It talks to the make.fun env over HTTP and plays the house gauntlet.

## Trial result

Budget 100k nodes/move (main.py 4,085 bytes of the 4,096 limit) — trial-0: 2 wins, 2 draws, 2 losses, Elo 1,279, above the practice floor (1,154). Mid-gauntlet vs the hardest practice opponents: Elo 1,445.

The first entry ran 200k nodes/move (trial-0 Elo 1,396 locally) but scored 0 in the practice sandbox: too slow on 1 CPU, it ran out of wall time. The rebuild cuts the budget to 100k, keeping the same strength on the mid-gauntlet (Elo 1,445) at a fraction of the time (414s of bot time in trial-0, no time losses). Smaller budgets were swept too — 25k and 50k both scored Elo 1,101, below the floor.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=ry8rmgrn&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
