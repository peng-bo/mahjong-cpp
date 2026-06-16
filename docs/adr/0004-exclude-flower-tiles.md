# Exclude flower tiles

The MCR rewrite will never model flower tiles. Excluding them keeps the public API, fan-calculator adapter, wall model, and expected-value calculations focused on the 34 standard tile types, even though some MCR scoring contexts can account for flower tile counts.
