AFFILIATION (LAW)
Affiliation governs NPC/faction response in active scenes only. NO background simulation.

TYPES:
REP (Global Reputation; single score)
REN (Faction Renown; per-faction score; overrides REP only inside that faction’s domain)

RANGES:
REP, REN ∈ [-100..+100]
REP has exactly ONE tier at all times; REN has ONE tier per faction.

TIER TABLES (CLOSED; derived from numeric value only):
REP:
-100 DREADED
-99..-70 FEARED
-69..-40 NOTORIOUS
-39..-15 INFAMOUS
-14..+14 UNKNOWN
+15..+39 NOTABLE
+40..+69 ADMIRED
+70..+99 REVERED
+100 LEGENDARY

REN:
-100 NEMESIS
-99..-75 RIVAL
-74..-50 ENEMY
-49..-25 FOE
-24..0 WARY
+1..+24 FAIR
+25..+49 TRUSTED
+50..+74 FRIEND
+75..+99 ALLY
+100 CHAMPION

CORE AXIOMS:
- NO_BACKGROUND_SIMULATION: affiliation has NO effect unless surfaced in an active scene.
- EXPLICIT_UPDATE_ONLY: REP/REN change ONLY via explicit Auto-Notes.
- NO_HIDDEN_MATH: tier must be computed from the declared numeric value via the closed tables.

UPDATE RULES:
- INVALID if REP/REN change is inferred from narration, time passage, or NPC reaction.
- REN update MUST name the faction.
- REP does not change unless explicitly Auto-Noted; REN does not change unless explicitly Auto-Noted.

DOMAIN RULE:
REN overrides REP only within the named faction’s domain/scope.

TIME DECAY (EXPLICIT ONLY):
- NO implicit time.
- Decay check may occur ONLY when CALENDAR advances ≥ 5 days AND no REP updates occurred during that span.
- Decay effect: REP moves 1 point toward 0; decay stops at current tier minimum.
- REN never decays unless explicitly declared.
- Decay MUST be Auto-Noted.

AUTO-NOTES (MANDATORY; sole persistence):
REP update:
<<Update Global Reputation to <value> (<tier>). Note: '<brief cause>'>>
REN update:
<<Update Faction '<FactionName>' Renown to <value> (<tier>).>>
REP decay:
<<Update Global Reputation to <value> (Decay).>>
