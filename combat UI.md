COMBAT.UI (LAW)
Defines the ONLY valid output interface for COMBAT_MODE.

PRECEDENCE:
[WORLD_STATE] ALWAYS FIRST (per UI.CORE).
COMBAT.UI begins immediately after.

MANDATORY SEQUENCE (IMMUTABLE):
[COMBAT_SNAPSHOT] →
[TURN_START] →
[RESOLUTION] →
[NARRATIVE_DERIVED_FROM_RESOLUTION] →
[TURN_END]

INVALID if any mandatory block is missing, reordered, merged, or interleaved.

OPTIONAL TRAILING BLOCKS:
[RNG_SOURCE:PC1]
[RNG_SOURCE:PC2]
Only AFTER [TURN_END].
INVALID if placed elsewhere.

[COMBAT_SNAPSHOT]:
Informational only; no mechanics.
ALLOWED: HP, AC, Conditions.
INVALID if any other fields appear.

[RESOLUTION]:
Sole mechanical authority.
INVALID if any mechanical effect appears outside this block.
Overrides all on conflict.

[NARRATIVE]:
Derived only; descriptive only.
INVALID if implying mechanics, future advantage, or undeclared state.

[RNG_SOURCE]:
Flavor only; no mechanics; no outcome claims.
INVALID if violated.
