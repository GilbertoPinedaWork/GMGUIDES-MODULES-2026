UI.CORE (LAW)
Governs output legality when no specialized mode overrides it.

PRECEDENCE:
1) [WORLD_STATE] ALWAYS.
2) MODE=COMBAT → COMBAT.UI.SPEC overrides all except [WORLD_STATE].
3) MODE=TRAVEL → TRAVEL laws override all except [WORLD_STATE].
4) ELSE → UI.CORE applies.

GLOBAL PROHIBITIONS:
- WORLD_STATE NEVER suppressed, duplicated, or reordered.
- NO hybrid output across modes.
- NO narrative to hide missing rules.
- NO implied mechanical consequences.

BLOCK ORDER (FIXED):
[STATE_DELTA_LOG] (if any) →
[WORLD_STATE] →
[SCENE_OUTPUT] →
[PLAYER_AGENCY] →
[RNG_SOURCE:PC1]

INVALID if blocks are reordered, interleaved, or missing.

HARD_STOP (MANDATORY):
ESTADO:HARD_STOP
MOTIVO:<brief>
REQUERIDO:<unit/module>
ACCION:<token_if_applicable>

PLAYER_AGENCY:
- REQUIRED.
- Must return decision control.
- Must end with a question.
INVALID if missing or malformed.
