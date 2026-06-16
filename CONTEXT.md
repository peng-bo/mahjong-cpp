# Mahjong Rules Engine

This context describes the mahjong rules vocabulary used by the library. It exists so rule-set changes use precise game terms instead of mixing Japanese riichi mahjong concepts with Chinese Official Mahjong concepts.

## Language

**Chinese Official Mahjong / MCR**:
The target ruleset defined by Chinese Mahjong competition rules, with scoring based on recognized fan patterns and an 8-point minimum to win.
_Avoid_: Guobiao, Chinese mahjong, riichi mahjong

**Flower Tiles**:
Optional bonus tiles that are outside this library's MCR model and scoring scope.
_Avoid_: Flowers, season tiles, plant tiles

**Legal Win**:
An MCR winning hand whose recognized fan total meets or exceeds the 8-point minimum.
_Avoid_: Agari, yaku-valid win

**Seat Wind**:
The wind assigned to the player whose hand is being evaluated.
_Avoid_: Player wind, self wind

**Round Wind**:
The prevailing wind of the current hand.
_Avoid_: Prevalent wind, field wind

**Self Draw**:
A win completed by drawing the winning tile oneself; this library's MCR evaluation treats every win as self draw.
_Avoid_: Tsumo

**Standard Tile Set**:
The 34 tile types used by MCR scoring in this library: three numbered suits and seven honor tiles, excluding red fives and flower tiles.
_Avoid_: 37-tile set, red dora tile set

**Meld**:
A revealed or declared tile group supplied to MCR scoring, such as a chow, pong, open kong, closed kong, or added kong.
_Avoid_: Call, naki

**Fan**:
An MCR scoring pattern with an associated point value.
_Avoid_: Yaku, han

**Total Fan**:
The sum of recognized MCR fan values for an evaluated hand after fan-calculator exclusions are applied.
_Avoid_: Score points, payment points
