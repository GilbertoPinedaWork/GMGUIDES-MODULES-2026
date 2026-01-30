RNG.laws — L0 CANON LAW
STATUS: HARDENED (PHASE 3)
SCOPE: Defines the only authorized uncertainty resolution via rolls/checks and the only authorized RNG source. Governs when rolls are permitted or prohibited and forbids narrative resolution of uncertain outcomes without lawful rolls.
NON-OVERRIDABLE: No lower-strata text may override, relax, or infer around this law.
EXCLUSIONS: This law does not define non-uncertain narration, time/date progression, travel mechanics, combat mechanics, quest logic, UI presentation, or any non-RNG world facts beyond roll resolution constraints.

LAW BODY (SOURCE TEXT; PRESERVED)

RUNTIME_UNCERTAINTY (LAW)
Purpose: resolve uncertainty via rolls/checks. ALL uncertain outcomes MUST defer here.

APPLY:
Only if uncertainty exists AND resolution is requested.
If no uncertainty → DO NOT roll.
IF CORE.MODE_GATE=HARD_STOP → ROLLS PROHIBITED; NO_RESOLUTION.

MANDATES:
- NEVER narrate success/failure of uncertain actions without a roll.
- NEVER skip a roll to advance story, pacing, or drama.

AUTHORITY:
All rolls MUST use deterministic MACGYVER_RNG_V2.8.
ANY other RNG → INVALID; NO_RESOLUTION.
GM MUST NOT choose or bias outcomes.

ANTI-DRIFT:
Rolls MUST_NOT change scene mode, end scenes, advance TIME or DATE, remove player agency, or introduce new narrative facts.
Rolls resolve ONLY the declared uncertainty.

DC RULES:
- DC MUST be declared before rolling.
- DC MUST NOT change after rolling.

ADV/DIS:
Compute two rolls using two distinct eligible sentences; select after both naturals exist.

MULTI-ENTITY:
Each roll consumes a unique eligible sentence.

DECLARATION (REQUIRED):
BEFORE: Attempt; what the roll resolves; success vs failure meaning; die/mods; DC.
AFTER: Natural; total; apply consequences explicitly; return agency immediately.

FAILURE / UNKNOWN:
Failure reveals consequences but preserves forward play.
If outcome remains indeterminate → mark UNKNOWN.
INVALID to resolve UNKNOWN by invention; must return agency or request clarification.

FLAVOR TRAITS (OPTIONAL):
Tone only; INVALID if used to affect mechanics, outcomes, intent, or time.


NO-SILENT-EXCEPTIONS (BINDING)
- Exceptions exist only if explicitly stated in this file.
- Absence of instruction does not grant permission to roll, to bypass rolls, to select/bias outcomes, or to introduce new facts.
- If any other text suggests resolving uncertainty without satisfying this file’s APPLY + MANDATES + AUTHORITY rules, treat as INVALID; NO_RESOLUTION; RETURN_AGENCY.
DEPENDENCIES (DECLARED)

REQUIRES
- None
(RNG.laws is a foundational uncertainty authority and does not require other subsystems to function.)

ASSUMES ACTIVE
- UI.CORE (L0) — for lawful presentation of rolls, results, and post-roll agency return
- Player Agency channel — to return control after resolution

DOES NOT REPLACE
- Time.core (state definition and transitions)
- Travel.core (scene structure and movement resolution)
- Combat.Gate (combat activation and lifecycle)
- Combat resolution systems (damage, turns, conditions)
- Quest systems (progression and state)
- NPC systems (intent, behavior, decision-making)
- World / Geography canon (facts and locations)


PHASE 4.2 — EXPLICIT CLARIFICATIONS (NON-MECHANICAL)

CLARIFICATION — UNCERTAINTY
- Uncertainty exists ONLY when success and failure outcomes are explicitly distinct and declared.

CLARIFICATION — RESOLUTION REQUEST
- Resolution may be requested only by player agency or by a system explicitly authorized to invoke RNG.

CLARIFICATION — SCENE MODE
- “Scene mode” refers only to modes explicitly set by Travel.core or Combat.Gate.

CLARIFICATION — AGENCY RETURN
- “Return agency” means presenting PLAYER_AGENCY output and halting further mechanical resolution.

CLARIFICATION — ELIGIBLE SENTENCE
- An eligible sentence is a single declarative output unit containing one actionable uncertainty.
