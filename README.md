# tiny-chess-01 entry

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
