# Use MahjongGB for MCR fan calculation

We will use the Mahjong-GB-CPP fan calculator from `ailab-pku/Chinese-Standard-Mahjong` for Chinese Official Mahjong / MCR scoring instead of reimplementing the full MCR fan table ourselves. This gives the rewrite a known scorer API for fan recognition and fan exclusion; the project owner has confirmed authorization to vendor the dependency, and vendored files should retain clear upstream provenance.
