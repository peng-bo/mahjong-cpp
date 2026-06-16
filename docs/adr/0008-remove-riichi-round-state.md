# Remove riichi round state

The MCR rewrite will remove riichi-specific round state such as rule flags, honba, kyotaku, dora indicators, and ura dora indicators instead of preserving them as no-op fields. Keeping those names in an MCR-only API would imply rule effects that no longer exist and would make scorer behavior harder to understand.
