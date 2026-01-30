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
DEPENDENCIES (DECLARED)

REQUIRES
- None
(UI.CORE is a foundational legality layer and does not require other subsystems to function.)

ASSUMES ACTIVE
- Time.core (L0) — for inclusion of WORLD_STATE time data when present
- Combat.UI.SPEC (L0/L1, when MODE=COMBAT) — for specialized combat UI blocks
- Travel.core (L0, when MODE=TRAVEL) — for travel-mode legality rules
- Player Agency channel — to return control and decisions

DOES NOT REPLACE
- Combat.Gate (combat activation and lifecycle)
- RNG.laws (roll authority and resolution)
- Travel.core (scene and movement resolution)
- Quest systems (progression and state)
- NPC systems (intent and behavior)
- World / Geography canon


PHASE 4.2 — EXPLICIT CLARIFICATIONS (NON-MECHANICAL)

CLARIFICATION — “SPECIALIZED MODE OVERRIDES”
- “Overrides” refers only to legality/formatting rules for output structure, not to mechanics.
- UI.CORE cannot authorize or imply mechanics; it only validates presentation.

CLARIFICATION — MODE SELECTION
- MODE=COMBAT and MODE=TRAVEL are valid only when explicitly activated by their governing L0 laws (Combat.Gate / Travel.core).
- If mode activation is missing or ambiguous, UI must follow HARD_STOP, not infer a mode.

CLARIFICATION — “NO HYBRID OUTPUT ACROSS MODES”
- Hybrid means mixing block rules or mechanics from different modes in a single output.
- This prohibition applies even if the narrative would benefit.

CLARIFICATION — “NO NARRATIVE TO HIDE MISSING RULES”
- If required governing rules are absent, output must enter HARD_STOP instead of improvising.

CLARIFICATION — WORLD_STATE
- WORLD_STATE is descriptive state reporting only.
- WORLD_STATE MUST NOT introduce new facts; it reports only declared/authorized state.
