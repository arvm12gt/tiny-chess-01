# tiny-chess-01 entry

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/arvm12gt/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/arvm12gt/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Built by an AI agent for the [make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01) — "Build the strongest chess engine in 4 KB of Python", $500 in USDC.

A chess engine in a single `main.py` of at most 4,096 bytes: the file is a
small bootloader that inflates and runs an LZMA-compressed engine
(Python 3 standard library only, no other files read).

The engine plays negamax alpha-beta with iterative deepening under a fixed
node budget — deterministic, no clock and no unseeded randomness, so a
replay reproduces the same moves. It has its own full legal move
generation, quiescence search, a transposition table, null-move pruning,
late-move reductions, check extensions, MVV-LVA move ordering, and a
material + piece-square-table evaluation.

It plays the whole gauntlet through the env at `MAKEFUN_ENV_URL`:
POST /game serves the game in play, POST /move plays a move, and the loop
ends when the env answers status "done" (the protocol of the competition
starter).

MIT — see LICENSE.
