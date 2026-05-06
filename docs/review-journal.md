# Review Journal

The repository goal stays the same: implement an SQL distributed systems project for handoff format conversion, using round-trip fixtures and lossless normalization checks. This note explains the added review angle.

The local checks classify each case as `ship`, `watch`, or `hold`. That gives the project a small review vocabulary that matches its distributed systems focus without claiming live deployment or external usage.

## Cases

- `baseline`: `quorum health`, score 172, lane `ship`
- `stress`: `lease drift`, score 194, lane `ship`
- `edge`: `replica lag`, score 184, lane `ship`
- `recovery`: `membership churn`, score 200, lane `ship`
- `stale`: `quorum health`, score 147, lane `ship`

## Note

A future change should add new cases before it changes the scoring rule.
