UI.CORE — L0 CANON LAW
STATUS: HARDENED (PHASE 3 — CORRECTED SOURCE)
SCOPE: Defines the sole legal UI output structure and legality rules when no specialized mode overrides apply. Governs block order, precedence between modes, hard-stop behavior, and player agency requirements.
NON-OVERRIDABLE: No lower-strata text may override, relax, reorder, or infer around this law.
EXCLUSIONS: This law does not define combat mechanics, travel mechanics, RNG outcomes, time progression, narrative content itself, or world facts beyond UI legality and structure.

LAW BODY (SOURCE TEXT; PRESERVED VERBATIM)

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


NO-SILENT-EXCEPTIONS (BINDING)
- UI legality is binary: VALID or INVALID.
- Absence of instruction does not permit block omission, reordering, merging, or implied mechanics.
- If any output violates precedence, block order, HARD_STOP format, or PLAYER_AGENCY requirements, treat as INVALID_UI; HALT_PRESENTATION.
