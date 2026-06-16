Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Replace riichi-specific round state with minimal MCR round state. The public model should keep only Round Wind at the round level and Seat Wind at the player or scoring context level, with all wins evaluated as Self Draw.

## Acceptance criteria

- [ ] Riichi-only round fields such as dora indicators, ura dora indicators, honba, kyotaku, and rule flags are removed or made unavailable from the MCR API.
- [ ] Round Wind is represented clearly in the MCR public model.
- [ ] Seat Wind is represented clearly in the MCR public model.
- [ ] Scoring tests show wind-related context is passed through to MahjongGB.
- [ ] No scoring path depends on riichi win flags.

## Blocked by

- `.scratch/mcr-rewrite/issues/02-introduce-mcr-scoring-result-and-public-calculator-api.md`
