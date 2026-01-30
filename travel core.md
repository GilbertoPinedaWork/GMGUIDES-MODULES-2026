TRAVEL.core — L0 CANON LAW
STATUS: HARDENED (PHASE 3)
SCOPE: Defines the only authorized TRAVEL scene entry, leg declaration, and resolution constraints. Governs TRAVEL_MODE_ACTIVE behavior and forbids implicit travel consequences.
NON-OVERRIDABLE: No lower-strata text may override, relax, or infer around this law.
EXCLUSIONS: This law does not define route data, region/climate facts, uncertainty mechanics details beyond delegation, combat resolution, NPC/quest systems, or any TIME change beyond the explicit prohibition below.
 
DEPENDENCIES (DECLARED)


LAW BODY (SOURCE TEXT; PRESERVED)

TRAVEL (LAW)
Applies ONLY_IF: TRAVEL_MODE_ACTIVE.
Purpose: resolve travel as a declared scene with no implicit consequences.

SCENE EXCLUSIVITY:
Travel resolution occurs ONLY within a declared travel scene.

LEG DECLARATION (MANDATORY; choose EXACTLY ONE):
A) LEG=UNEVENTFUL
B) LEG=UNCERTAIN
If declaration missing or ambiguous → NOT_RESOLVED; NO_ROLLS; NO_NARRATION; ask clarification.

NO_IMPLICIT_CONSEQUENCES:
Consequences (risk, loss, surprise) ONLY_IF explicitly declared pre-resolution.

NO_IMPLICIT_TIME:
Travel never advances TIME.
TIME change ONLY_IF explicitly declared and routed via TIME system.

LEG=UNEVENTFUL:
- No rolls.
- Effect: location change only.
- INVALID if narration implies risk, loss, surprise, or hidden mechanics.

LEG=UNCERTAIN:
- MUST use TRAVEL.UNCERTAINTY.PROTOCOL.
- All rolls MUST use RUNTIME_UNCERTAINTY_SYSTEM.
- Valid uncertainties only:
{DETECTION_RISK, ENVIRONMENTAL_COMPLICATION, DELAY_OR_OBSTRUCTION, RESOURCE_STRAIN}
- INVALID to resolve uncertainty directly here.

PROHIBITIONS:
- No invented encounters, factions, or lore.
- No combat mechanics.
- No damage or conditions.
- INVALID if NPC takes mechanical action without declared uncertainty and NPC involvement.

SCENE END:
Travel scene MUST end explicitly after resolution.
Scene end ≠ TIME advance.

HOSTILITY:
Explicit hostility → RETURN_TO_GATE; combat never resolved here.

INTEGRATION:
FA travel rules apply ONLY_IF FA_ACTIVE.


NO-SILENT-EXCEPTIONS (BINDING)
- Exceptions exist only if explicitly stated in this file.
- Absence of instruction does not grant permission to infer travel consequences, rolls, encounters, or TIME changes.
- If any other text implies travel effects without satisfying this file’s SCENE + LEG declaration requirements, treat as INVALID; NOT_RESOLVED; NO_ROLLS; NO_NARRATION.

REQUIRES
- Time.core (L0) — for explicit TIME routing when a TIME change is lawfully declared
- RNG.laws (L0) — for all uncertainty resolution via TRAVEL.UNCERTAINTY.PROTOCOL

ASSUMES ACTIVE
- UI.CORE (L0) — for lawful presentation of travel scenes and outcomes
- World / Geography canon — for location identity only (not effects)

DOES NOT REPLACE
- Time.core (state definition and transitions)
- RNG.laws (authority over rolls and uncertainty)
- Combat.Gate (combat activation and resolution)
- NPC systems (behavior and agency)
- Quest systems (progression and triggers)
- Route, climate, or region data files (descriptive inputs only)

PHASE 4.2 — EXPLICIT CLARIFICATIONS (NON-MECHANICAL)

CLARIFICATION — SCENE DEFINITION
- A travel scene exists ONLY when TRAVEL_MODE_ACTIVE is explicitly set by the system.

CLARIFICATION — CONSEQUENCES
- “Consequences” means risk, loss, delay, encounter, discovery, or resource change.
- None may occur unless explicitly declared before resolution.

CLARIFICATION — LOCATION
- Location identity is descriptive only and sourced from World / Geography canon.
- No effects are implied by location change alone.

CLARIFICATION — FA (FOREST OF ALLANAR)
- “FA” refers exclusively to the Forest of Allanár.
- FA travel rules apply ONLY_IF FA_ACTIVE explicitly indicates the Forest of Allanár context.
- If FA_ACTIVE is false or undefined, FA rules are inert.

CLARIFICATION — NPC INVOLVEMENT
- NPC involvement means an NPC is explicitly declared as a participant subject to RNG or Combat systems.
