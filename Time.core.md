TIME.core — L0 CANON LAW
STATUS: HARDENED (PHASE 3)
SCOPE: Defines the global TIME state representation and the only authorized TIME state transitions.
NON-OVERRIDABLE: No lower-strata text may override, relax, or infer around this law.
EXCLUSIONS: This law does not grant (or imply) numeric time, durations, schedules, mechanical modifiers, or any non-fiction effects beyond what is explicitly allowed below.

LAW BODY (SOURCE TEXT; PRESERVED)

TIME (LAW)
REP: TIME:S [T]; exactly one S.

S∈{PRE_DAWN,DAWN,MORNING,MIDDAY,AFTERNOON,DUSK,EVENING,NIGHT}
ORDER: PRE_DAWN>DAWN>MORNING>MIDDAY>AFTERNOON>DUSK>EVENING>NIGHT>PRE_DAWN
ANY_OTHER_STATE → INVALID; NO_CHANGE.

T∈{QUIET,BUSY,TENSE,FESTIVE,ALERT,DROWSY};
optional; max1; explicit only;
T never implies duration, passage, escalation, or decay.

NO_IMPLICIT: narration, travel, pacing, fatigue, combat rounds ≠ TIME change.
INVALID if inferred from narration, resolution, feeling, distance, fatigue, or pacing.

CHANGE only if explicit and authorized:
- PLAYER explicit request, or
- SYSTEM declaration with explicit target S.
OPS: STEP_NEXT | JUMP(S) | TAG(T|NONE) | SET(S,T|NONE)

AMBIGUOUS / NO_TARGET / INVALID_S → NO_CHANGE; MUST ask clarification; MUST NOT guess.

FX+ (fiction only): availability, ambience/tone, light/sound.
FX- (never): advantage/disadvantage, DCs, conditions, damage, schedules,
NPC commitments, new lore, numeric time/duration.

COMBAT/TRAVEL: no default TIME advance.


NO-SILENT-EXCEPTIONS (BINDING)
- Exceptions exist only if explicitly stated in this file.
- Absence of instruction does not grant permission to infer a TIME change.
- If any other text implies TIME changes without meeting this file's CHANGE rule, treat as INVALID; NO_CHANGE.
