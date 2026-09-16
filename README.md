# Poker Brain

Post-session review tool for CoinPoker play. A single self-contained page —
no build step, no dependencies, no server code.

Deployed to GitHub Pages the same way as `wanderloot-app`: plain HTML at the
repo root, served from `main`.

## Regenerating

The page is generated from hand histories by the tool in the `Poker App`
project on the desktop:

```bash
python -m pokerbrain report --out site/index.html
```

Then commit and push from this folder. Pages picks it up within a minute.

## What is in it

- **Overview** — result, showdown / non-showdown split, cumulative graph, and
  your stats beside the pool's.
- **Hands** — every hand replayed on a felt table, with pot odds, SPR, MDF and
  equity against an estimated range for each decision.
- **Leaks** — findings ranked by how much the sample actually supports them.
- **Opponents** — players reconstructed across CoinPoker's rotating export IDs
  by seat and stack continuity.
- **Player tags** — type ten HUD stats, get a colour tag, the exploits, and a
  note sized for the client's 250-character field.

## Note on the hosted version

Screenshot reading is not available here. It depends on a Claude runtime that
only exists inside a published Artifact, so on this host the Player tags tab
is entry-only. Use the quick entry box — all ten numbers on one line.

## Privacy

This page is public. It contains real hand histories, results and play
patterns. Opponents are not identifiable — CoinPoker's export replaces their
names with per-hand IDs — but the play shown is real.
