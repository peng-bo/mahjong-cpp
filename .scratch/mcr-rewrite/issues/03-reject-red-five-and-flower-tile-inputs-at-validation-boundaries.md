Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Update hand construction and validation so the library accepts only the 34 Standard Tile Set. Red-five notation and Flower Tiles should be rejected at input boundaries instead of silently normalized or ignored.

## Acceptance criteria

- [ ] Inputs such as `0m`, `0p`, and `0s` are invalid.
- [ ] The hand and wall model use exactly 34 standard tile types.
- [ ] Flower Tiles are not representable through the public MCR API.
- [ ] Existing validation errors are updated to use MCR vocabulary.
- [ ] Tests cover red-five rejection and standard-tile acceptance.

## Blocked by

- `.scratch/mcr-rewrite/issues/02-introduce-mcr-scoring-result-and-public-calculator-api.md`
