Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Convert expected-score calculation so its value is expected Total Fan under MCR scoring. Completed hands below the 8-fan Legal Win threshold should contribute zero value, and wall construction should use the 34 Standard Tile Set with optional custom wall input.

## Acceptance criteria

- [ ] Expected-score output is expressed as expected Total Fan.
- [ ] Completed hands below 8 Total Fan contribute zero expected value.
- [ ] Default wall construction uses four of each standard tile minus the player's concealed hand and Melds.
- [ ] Callers can provide a custom wall.
- [ ] The initial shanten model remains regular hands, seven pairs, and thirteen orphans.
- [ ] Tests cover expected value behavior around the 8-fan threshold.

## Blocked by

- `.scratch/mcr-rewrite/issues/02-introduce-mcr-scoring-result-and-public-calculator-api.md`
- `.scratch/mcr-rewrite/issues/03-reject-red-five-and-flower-tile-inputs-at-validation-boundaries.md`
- `.scratch/mcr-rewrite/issues/04-replace-riichi-round-state-with-minimal-mcr-round-state.md`
