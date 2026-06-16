# Use minimal self-draw win context

The MCR rewrite will model win context with only seat wind and round wind, and will evaluate every win as self draw. This deliberately excludes ron-specific and event-specific states such as robbing a kong, replacement-tile wins, last-tile wins, and last-discard wins so score calculation and expected-score search stay aligned with the library's single-player draw/discard model.
