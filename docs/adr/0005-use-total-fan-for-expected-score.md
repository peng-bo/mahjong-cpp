# Use total fan for expected score

Expected score in the MCR rewrite will optimize for expected total fan, not settlement points. The expected-value model is a single-player draw/discard search, so total fan is a clearer and more honest objective than a payment-based score that would require modeling the other players and full hand settlement.
