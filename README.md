# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Alfatih15/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Alfatih15/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB chess engine in Python: 0x88 board, alpha-beta search with transposition table, iterative deepening and quiescence.

## Run it

```sh
python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=hjff56h1&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

## Engine

`main.py` is 3,783 bytes: the kit's `makefun compress` packs the readable source (`engine_src.py`, kept beside it uncommitted) into an LZMA payload. 0x88 board, negamax + alpha-beta, TT, iterative deepening, quiescence, null-move, LMR, PVS, killer moves, MVV-LVA. Fixed 70,000 nodes/move, deterministic, stdlib only.

Practice vs sunfish-4K: best trial Elo 1545 (full v6); the submitted slim build is estimated ~25-30 Elo below the 1451 trial. Perft exact: startpos 20/400/8902/197281/4865609, kiwipete 48/2039/97862/4085603.
