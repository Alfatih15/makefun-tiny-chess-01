# BUILD_LOG — tiny-chess-01

## Entry

- `main.py` **3,783 B** (cap 4,096), packed by the kit's
  `makefun compress` from readable `engine_src.py` (12,682 B,
  sha256 ad4a5c343b382…). Round-trip: decompresses byte-identical.
- Snapshot: main.py 3,783 + LICENSE 1,104 + README + this file +
  `.makefun/owner.json` 57 — under the 8,192 cap.
- Wallet: `Cfdgeggmd6ij5dLpqwmqAaGExTbi4JPZJYcRdi4iSjSW`.

## Engine

v6 (strongest built): 0x88, TT, null-move R=2, LMR, PVS, check extension,
killer + history heuristic, Michniewski PSTs, pawn structure, bishop-pair,
endgame king table. Trials: 1545 / 1191 / 1279, mean 1338 (sunfish 1,365).

## Why slim

2-trial limit: trials v11=1191, v12=1451 — neither beat 1451, so tuning
stopped. Full v6 packs to **5,447 B** (over cap). Slimming removed post()
error handling, a redundant null-move try/except, a dead TT-flag line,
history heuristic, pawn-structure eval, bishop-pair + endgame king table
→ 3,783 B. Slim trial Elo **unmeasured**; removals cost ~25–30 Elo est.

## Packing

The first packed main.py (4,062 B) used the builder's own LZMA-9 +
base85 packer, which the authorship check does not credit. Replaced by
hand-rewriting `engine_src.py` (file tools only) and packing with the
kit's own `makefun compress` as its own command after the last source
write. v6 17,713 B → slim readable 12,682 B → 3,783 B.

## Verification (not a trial)

- Perft exact (see README). Differential choose: readable vs packed,
  same move on 8 positions. Smoke test vs local env (trial-0, killed
  mid-game-2): 45/45 moves HTTP 200, 0.92–2.54 s/move, game 1 won by mate.
