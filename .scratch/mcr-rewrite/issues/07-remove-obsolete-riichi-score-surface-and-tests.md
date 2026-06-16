Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Remove obsolete riichi scoring surface and rewrite or delete tests whose expectations depend on Japanese riichi mahjong. The final codebase should not expose active APIs for riichi yaku, han, fu, dora, ura dora, red dora, honba, kyotaku, or limit-hand score titles.

## Acceptance criteria

- [ ] Riichi scoring APIs are removed from the active public surface or replaced by MCR-specific APIs.
- [ ] Tests that asserted riichi scoring behavior are removed or rewritten for MCR behavior.
- [ ] Documentation no longer advertises riichi score calculation as supported.
- [ ] The build and test suite pass without riichi score fixtures.
- [ ] Remaining terminology follows the project glossary.

## Blocked by

- `.scratch/mcr-rewrite/issues/02-introduce-mcr-scoring-result-and-public-calculator-api.md`
- `.scratch/mcr-rewrite/issues/03-reject-red-five-and-flower-tile-inputs-at-validation-boundaries.md`
- `.scratch/mcr-rewrite/issues/04-replace-riichi-round-state-with-minimal-mcr-round-state.md`
- `.scratch/mcr-rewrite/issues/05-add-mcr-scoring-samples-and-documentation.md`
- `.scratch/mcr-rewrite/issues/06-convert-expected-score-calculation-to-expected-total-fan.md`
