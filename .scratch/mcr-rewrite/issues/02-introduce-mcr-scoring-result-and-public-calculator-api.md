Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Introduce the project-owned MCR scoring API around MahjongGB. Callers should evaluate a completed hand using MCR-specific types and receive a result containing Legal Win status, Total Fan, and recognized Fan entries. The implementation should evaluate wins as Self Draw and use only Seat Wind and Round Wind as win context.

## Acceptance criteria

- [ ] The project exposes MCR-specific scoring API names rather than reusing riichi-oriented names.
- [ ] The result shape includes Legal Win status, Total Fan, and Fan entries.
- [ ] Hands below 8 Total Fan are not Legal Wins but can expose recognized Fan details.
- [ ] Seat Wind and Round Wind are accepted as the only public win-context inputs.
- [ ] The adapter calls MahjongGB internally without exposing MahjongGB types.
- [ ] Golden tests verify known MahjongGB examples through the project API.

## Blocked by

- `.scratch/mcr-rewrite/issues/01-vendor-mahjonggb-and-wire-the-build.md`
