Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Update user-facing samples and documentation to demonstrate MCR scoring through the project API. The documentation should explain Fan, Total Fan, Legal Win, Self Draw, Seat Wind, Round Wind, Standard Tile Set, and the absence of Flower Tiles and riichi-only concepts.

## Acceptance criteria

- [ ] Sample code demonstrates evaluating at least one Legal Win.
- [ ] Sample code demonstrates a completed hand below 8 Total Fan being rejected as not legal.
- [ ] README or equivalent docs describe the MCR-only scope.
- [ ] Docs no longer present riichi score calculation as the active rules model.
- [ ] Sample output uses Fan and Total Fan terminology.

## Blocked by

- `.scratch/mcr-rewrite/issues/02-introduce-mcr-scoring-result-and-public-calculator-api.md`
- `.scratch/mcr-rewrite/issues/03-reject-red-five-and-flower-tile-inputs-at-validation-boundaries.md`
- `.scratch/mcr-rewrite/issues/04-replace-riichi-round-state-with-minimal-mcr-round-state.md`
