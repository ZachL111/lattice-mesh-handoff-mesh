# Lattice Mesh Handoff Mesh Walkthrough

This walk-through keeps the domain vocabulary close to the data instead of burying it in prose.

| Case | Focus | Score | Lane |
| --- | --- | ---: | --- |
| baseline | quorum health | 172 | ship |
| stress | lease drift | 194 | ship |
| edge | replica lag | 184 | ship |
| recovery | membership churn | 200 | ship |
| stale | quorum health | 147 | ship |

Start with `recovery` and `stale`. They create the widest contrast in this repository's fixture set, which makes them better review anchors than the middle cases.

`recovery` is the optimistic case; use it to make sure the scoring path still rewards strong signal.
