# lattice-mesh-handoff-mesh

`lattice-mesh-handoff-mesh` is a compact SQL repository for distributed systems, centered on this goal: Implement an SQL distributed systems project for handoff format conversion, using round-trip fixtures and lossless normalization checks.

## Problem It Tries To Make Smaller

This is intentionally local and self-contained so it can be inspected without credentials, services, or seeded history.

## Lattice Mesh Handoff Mesh Review Notes

Start with `membership churn` and `quorum health`. Those cases create the widest score spread in this repo, so they are the best quick check when the model changes.

## Working Pieces

- `fixtures/domain_review.csv` adds cases for quorum health and lease drift.
- `metadata/domain-review.json` records the same cases in structured form.
- `config/review-profile.json` captures the read order and the two review questions.
- `examples/lattice-mesh-handoff-walkthrough.md` walks through the case spread.
- The SQL code includes a review path for `membership churn` and `quorum health`.
- `docs/field-notes.md` explains the strongest and weakest cases.

## Design Notes

The core code exposes a scoring path and the added review layer uses `signal`, `slack`, `drag`, and `confidence`. The domain terms are `quorum health`, `lease drift`, `replica lag`, and `membership churn`.

The SQL checks add a separate view over the domain review fixture.

## Example Run

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File scripts/verify.ps1
```

## Tests

That command is also the regression path. It verifies the domain cases and catches mismatches between the CSV, metadata, and code.

## Known Limits

The fixture set is small enough to audit by hand. The next useful expansion is malformed input coverage, not extra surface area.
