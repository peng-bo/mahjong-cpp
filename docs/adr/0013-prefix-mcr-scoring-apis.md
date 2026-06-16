# Prefix MCR scoring APIs

Scoring APIs in the rewrite will use MCR-specific names such as `MCRScoreCalculator`, `MCRExpectedScoreCalculator`, and `MCRResult` instead of reusing the existing generic riichi-oriented names. The project history makes rule-domain ambiguity likely, so explicit MCR names are worth the breaking API change.
