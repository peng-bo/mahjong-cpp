Status: ready-for-agent

## Parent

`.scratch/mcr-rewrite/PRD.md`

## What to build

Vendor the authorized MahjongGB fan calculator under the third-party dependency area and make the project build it as an internal dependency. Preserve clear upstream provenance in the vendored files or adjacent documentation, and keep MahjongGB out of the public API.

## Acceptance criteria

- [ ] MahjongGB source is available under the agreed third-party location.
- [ ] The build system compiles or otherwise links MahjongGB for project-owned code to call.
- [ ] No public library header exposes MahjongGB types directly.
- [ ] Vendored source or companion documentation records the upstream source clearly.
- [ ] A minimal build or compile test proves the dependency is reachable.

## Blocked by

None - can start immediately
