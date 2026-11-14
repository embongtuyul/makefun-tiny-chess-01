# tiny-chess-01 entry

A chess engine in one packed `main.py` (makefun-compress/v1 LZMA stub over
the readable source `engine.py`, kept beside it uncommitted). 0x88 board,
alpha-beta with iterative deepening under a fixed node budget (never a
clock), quiescence over captures/promotions and check evasions, transposition
table, MVV-LVA + killer move ordering, material + piece-square evaluation
with phase-interpolated king tables and a bishop-pair bonus, and repetition /
fifty-move draws scored inside the search. Every move derives from the
position, the game history and nothing else, so live and replay trials agree.

It plays the 8-game house gauntlet through the env at `MAKEFUN_ENV_URL`
(`POST /game`, `/move`, `/resign`), resigning only lost-or-mated positions.
