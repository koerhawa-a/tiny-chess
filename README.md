# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/koerhawa-a/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/koerhawa-a/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python: 0x88 board, negamax alpha-beta with quiescence, transposition table, killer and history ordering, null-move pruning, LMR, and a tapered piece-square evaluation. It searches to a fixed node budget per move, never to a clock, so every game replays deterministically. It talks to the make.fun env over HTTP and plays the house gauntlet.

## Trial result

Budget 200k nodes/move — trial-0: 7 wins, 2 draws, 7 losses, Elo 1,396, above the sunfish baseline (1,360).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=ry8rmgrn&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
