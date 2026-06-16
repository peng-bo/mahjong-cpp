Status: ready-for-agent

## Problem Statement

The library currently implements Japanese riichi mahjong scoring and expected-score calculation. Its public model and internal scoring code are deeply tied to riichi concepts such as riichi, dora, ura dora, red dora, fu, honba, kyotaku, yaku, and limit-hand score titles. The project needs to become a Chinese Official Mahjong / MCR library instead, with scoring based on MCR fan recognition and an 8-point minimum Legal Win.

## Solution

Rewrite the rules-facing parts of the library as an MCR-only implementation. The library will expose MCR-specific APIs, use the 34 Standard Tile Set, exclude Flower Tiles, evaluate every win as Self Draw, and use Seat Wind and Round Wind as the only win-context inputs. MCR fan recognition will be delegated to the vendored MahjongGB fan calculator behind a project-owned adapter. Score results will return recognized Fan entries, Total Fan, and whether the hand is a Legal Win. Expected score will use expected Total Fan rather than settlement points.

## User Stories

1. As a library user, I want to evaluate a completed MCR hand, so that I can see whether it is a Legal Win.
2. As a library user, I want the score result to expose recognized Fan entries, so that I can explain why a hand received its Total Fan.
3. As a library user, I want hands below 8 Total Fan to be marked as not legal while still showing fan details, so that I can debug near-miss hands.
4. As a library user, I want scoring APIs named with MCR-specific terms, so that I do not confuse them with Japanese riichi scoring.
5. As a library user, I want the library to reject red-five notation, so that all hand inputs match the 34 Standard Tile Set.
6. As a library user, I want Flower Tiles to be excluded entirely, so that scoring and expected-score behavior stay simple and predictable.
7. As a library user, I want Seat Wind and Round Wind to affect scoring where MCR fan rules require them, so that wind-related fans are evaluated correctly.
8. As a library user, I want all scoring to be treated as Self Draw, so that the library matches its single-player draw/discard model.
9. As a library user, I want Meld information to be preserved for chow, pong, open kong, closed kong, and added kong, so that MCR fan recognition can distinguish exposed and declared groups.
10. As a library user, I want MahjongGB to be hidden behind project-owned API types, so that my code does not depend directly on the upstream scorer's API.
11. As a library maintainer, I want vendored MahjongGB code to live in a separate third-party area, so that upstream provenance stays clear.
12. As a library maintainer, I want adapter tests around MahjongGB integration, so that tile encoding and Meld conversion mistakes are caught early.
13. As a library maintainer, I want removed riichi concepts to fail at the API boundary, so that MCR behavior is not silently affected by obsolete fields.
14. As a library user, I want expected-score calculation to optimize for Total Fan, so that the result matches MCR fan scoring rather than Japanese point settlement.
15. As a library user, I want completed hands below the 8-fan minimum to contribute zero expected value, so that impossible wins do not distort expected-score output.
16. As a library user, I want the existing shanten, necessary-tile, and unnecessary-tile behavior to continue as the initial search model, so that MCR scoring can be integrated before deeper MCR-specific shape search is attempted.
17. As a library user, I want default wall construction to use only my visible self state, so that simple expected-score calls work without full-table information.
18. As an advanced caller, I want to provide a custom wall, so that I can account for additional known unavailable tiles.
19. As a sample user, I want sample programs to demonstrate MCR scoring, so that I can learn the new API without reading internals.
20. As a maintainer, I want documentation to describe MCR semantics and out-of-scope riichi concepts, so that future work does not accidentally reintroduce Japanese rules.

## Implementation Decisions

- The project will be rewritten as MCR-only rather than preserving Japanese riichi mahjong as a parallel ruleset.
- MahjongGB will provide the MCR fan recognition engine; the project owner has confirmed authorization to vendor it.
- Vendored MahjongGB files will live under a third-party location with clear upstream provenance.
- MahjongGB will remain an internal dependency behind a project-owned adapter.
- Public scoring APIs will use MCR-specific names such as `MCRScoreCalculator`, `MCRExpectedScoreCalculator`, and `MCRResult`.
- Score results will be shaped around MCR Fan entries, Total Fan, and Legal Win status.
- Legal Win means Total Fan is at least 8.
- Hands below 8 Total Fan may return recognized Fan details but are not successful Legal Wins.
- Flower Tiles are permanently out of scope.
- The Standard Tile Set is exactly 34 tile types; red-five notation and semantics are removed.
- Win context is minimal: Seat Wind and Round Wind are retained, and every win is evaluated as Self Draw.
- Riichi-specific round state is removed rather than kept as no-op API surface.
- Meld types for chow, pong, open kong, closed kong, and added kong remain available because MCR scoring needs them.
- The initial shanten model remains regular hands, seven pairs, and thirteen orphans.
- Expected score uses expected Total Fan, not settlement points.
- Expected-score default wall construction uses four of each standard tile minus the player's concealed hand and Melds, with a custom wall override for callers who need one.

## Testing Decisions

- Tests should verify public behavior through project-owned APIs rather than through MahjongGB internals.
- Adapter golden tests should compare known MahjongGB examples through the project API.
- Boundary tests should verify that hands below 8 Total Fan are not Legal Wins while still exposing fan details.
- Validation tests should reject removed riichi concepts, especially red-five notation.
- Expected-score tests should verify that completed hands below 8 Total Fan contribute zero value and that expected value is expressed as Total Fan.
- Existing score-calculation, hand-string, and expected-score tests provide the closest prior art, but their expected values must be rewritten for MCR semantics.

## Out of Scope

- Keeping Japanese riichi scoring as a supported ruleset.
- Modeling Flower Tiles.
- Modeling ron, robbing a kong, replacement-tile wins, last-tile wins, last-discard wins, or other event-specific win context.
- Modeling payment settlement between players.
- MCR-aware shanten extensions for patterns such as knitted straight or lesser honors and knitted tiles.
- Full-table simulation of opponents, discards, calls, or defensive risk.
- Direct exposure of MahjongGB types as the library's public API.

## Further Notes

The expected-score rewrite depends on MCR score calculation being reliable first. Implementation should start with a narrow scorer adapter slice, then progressively replace removed riichi semantics and finally reconnect expected-score behavior to Total Fan.
