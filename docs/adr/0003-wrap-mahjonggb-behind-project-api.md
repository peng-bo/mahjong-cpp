# Wrap MahjongGB behind project API

MahjongGB will be an internal MCR fan-calculation dependency, not the public API of this library. The project will expose its own MCR-oriented player, round, win-context, and result types, with a thin adapter translating those types into MahjongGB inputs so callers are insulated from upstream API changes or a future scorer replacement.
