TRAVEL.UNCERTAINTY (LAW)
Applies ONLY_IF: TRAVEL_MODE_ACTIVE AND LEG=UNCERTAIN.
Purpose: resolve declared travel uncertainty without implicit consequences or invention.

REQUIRES: RUNTIME_UNCERTAINTY_SYSTEM.
EXCLUDES: combat resolution, damage, conditions, implicit time/date/moon, invented lore.

DECLARATION_FIRST (MANDATORY BEFORE ANY ROLL):
- TRAVEL_KIND ∈ {INTER_SETTLEMENT, INTRA_SETTLEMENT}
- ROUTE_PLAN (declared edges or named POIs only)
- UNCERTAINTY_TYPE ∈ {DETECTION_RISK, ENVIRONMENTAL_COMPLICATION, DELAY_OR_OBSTRUCTION, RESOURCE_STRAIN}
- STAKES (bounded, proportional)
Missing any → NOT_RESOLVED; HARD_STOP; request missing fields.

GOVERNING GRAPH:
If FA=ON → FA.TRAVEL.PROTOCOLS.
Else:
- INTER → WORLD.ROUTES.MAIN (read-only).
- INTRA → active settlement POIs required; otherwise HARD_STOP.
INVALID to introduce new nodes, edges, or POIs.

ROLLING:
ALL uncertainty rolls MUST use RUNTIME_UNCERTAINTY_SYSTEM.
Roll resolves ONLY the declared uncertainty.
INVALID to resolve without a roll when declaration requires one.

OUTCOMES (CLOSED SET; choose EXACTLY ONE or NONE):
INTER (EXPLICIT):
A1 NO_EVENT
A2 DETECTION_RISK (signs/alertness only; NO combat)
A3 ENVIRONMENTAL_COMPLICATION (friction) + optional FORCED_INTERMEDIATE_NODE (existing only)
A4 DELAY_OR_OBSTRUCTION (blocked edge/detour via existing edges/forced intermediate)
A5 RESOURCE_STRAIN (declared consumables only)

INTRA (IMPLICIT):
B1 FRICTION_ONLY (no mechanics)
B2 FORCED_INTERMEDIATE_POI (existing only)
B3 SOFT_DELAY (no time change unless explicitly declared elsewhere)
B4 RESOURCE_STRAIN (only if declared and tracked)

INVALID to apply more than one outcome template per resolution.
INVALID if FORCED_INTERMEDIATE_NODE/POI is not already declared and reachable.

PRESENTATION:
INTER → explicit scaffold (show roll block).
INTRA → implicit friction only; INVALID if implying mechanics or time.

COMBAT:
Explicit hostility → RETURN_TO_GATE; no combat mechanics here.

INTEGRATION:
Arrival does NOT auto-change TIME/DATE/MOON.
Any time/date change requires explicit declaration via TIME/CALENDAR.

INVALID IF ANY:
uncertainty without declaration;
outcome outside templates;
implicit time/date;
invented lore/encounters;
new nodes/edges/POIs;
combat mechanics in travel.
