COMBAT.GATE — L0 CANON LAW
STATUS: HARDENED (PHASE 3)
SCOPE: Defines the sole legal entry into Combat Mode, the mandatory activation conditions, and the atomic initialization boundary. Governs when combat may and may not exist.
NON-OVERRIDABLE: No lower-strata text may override, relax, bypass, or infer around this law.
EXCLUSIONS: This law does not define combat turn mechanics, damage resolution, condition effects, AI tactics, UI presentation, or post-combat cleanup beyond the gate and initialization boundary.

LAW BODY (SOURCE TEXT; PRESERVED)

COMBAT.GATE (LAW)
Combat exists ONLY_IF system declares: “Combat Mode is activated.”

PRE-ACTIVATION:
- No turns, actions, reactions, initiative, damage, or conditions.
- Any mechanical execution before activation → INVALID.

ACTIVATION REQUIRES ALL:
- ≥2 entities
- Explicit or imminent hostility
- Hostile action attempted or immediately imminent
- Not resolvable in free narrative

EXPLICIT TRIGGER (mandatory):
ATTACK | OFFENSIVE_SPELL | HARMFUL_OBJECT_USE

IMPLICIT IMMINENT TRIGGER (authorized only if ALL true):
CLEAR_HOSTILE_INTENT
IMMEDIATE_CONFLICT
TEMPORAL_ORDER_MATTERS

INVALID to activate combat from verbal threats, arguments, intimidation, or vague hostility alone.

ON ACTIVATION:
- Free narrative is frozen.
- Participants are identified.
- Initialization executes immediately and exactly once.

INITIALIZATION (ATOMIC):
- Determine participants (present, targetable, mechanically interactive).
- Lock participant list (no retroactive additions).
- Evaluate surprise for each participant (before initiative only).
- Surprise applies first round only.
- Roll initiative per rules; order fixed for entire combat.
- Set ROUND=1; CURRENT_TURN=first in order.

PROHIBITED DURING INITIALIZATION:
- Any actions, attacks, damage, conditions, reactions, or narrative interpolation.

ON COMPLETION:
- Enter turn cycle.
- Reverting to narrative mode is prohibited until combat ends by rule.


NO-SILENT-EXCEPTIONS (BINDING)
- Combat may exist ONLY if this gate is satisfied exactly.
- Absence of instruction does not permit early actions, soft activation, narrative damage, or retroactive justification.
- If any other text implies combat effects without a valid gate activation, treat as INVALID; COMBAT_NOT_ACTIVE; NO_MECHANICS.
DEPENDENCIES (DECLARED)

REQUIRES
- Time.core (L0) — for ordering, surprise timing, and round/turn semantics once combat is active
- RNG.laws (L0) — for initiative rolls and any uncertainty during initialization

ASSUMES ACTIVE
- UI.CORE (L0) — for lawful declaration of Combat Mode activation and initialization output
- Entity system (PC/NPC existence) — for identifying participants

DOES NOT REPLACE
- Combat turn resolution systems (actions, damage, conditions)
- Combat cleanup / end-of-combat rules
- RNG.laws (authority over rolls)
- Time.core (state definition and transitions)
- NPC systems (decision-making and intent)
- Quest systems (progression or triggers)
- World / Geography canon


PHASE 4.2 — EXPLICIT CLARIFICATIONS (NON-MECHANICAL)

CLARIFICATION — “NOT RESOLVABLE IN FREE NARRATIVE”
- This means temporal ordering and mechanical interaction are required to resolve the hostility.
- It does not permit narrative damage, conditions, or retroactive mechanics prior to activation.

CLARIFICATION — “IMMEDIATELY IMMINENT”
- “Immediately imminent” means the hostile action would occur next absent intervention.
- Verbal threats, posturing, or distant intent are insufficient.

CLARIFICATION — “PARTICIPANTS”
- Participants are entities explicitly declared as present and mechanically interactive.
- No participant may be assumed or added retroactively based on narrative inference.

CLARIFICATION — INITIALIZATION BOUNDARY
- Initialization performs only the listed setup steps.
- Any outcome resolution (hits, damage, conditions, reactions) is prohibited until after initialization completes.
