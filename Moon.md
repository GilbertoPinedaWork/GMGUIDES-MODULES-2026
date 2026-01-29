MOON (LAW)
MOON is DERIVED ONLY from CALENDAR date (YEAR, MONTH_INDEX, DAY). No manual set, no independent advance.

CYCLE=30 days.
PHASE∈{NEW_MOON,WAXING_CRESCENT,FIRST_QUARTER,WAXING_GIBBOUS,FULL_MOON,WANING_GIBBOUS,LAST_QUARTER,WANING_CRESCENT}

DERIVE:
ABS=(YEAR*360)+((MONTH_INDEX-1)*30)+(DAY-1); if YEAR omitted → 0
LDI=(ABS%30)+1  (1..30)
MAP (closed table):
1..3 NEW_MOON
4..7 WAXING_CRESCENT
8..11 FIRST_QUARTER
12..14 WAXING_GIBBOUS
15..17 FULL_MOON
18..21 WANING_GIBBOUS
22..25 LAST_QUARTER
26..30 WANING_CRESCENT

REP: MOON:<PHASE>  optional MOON_DAY:<LDI>/30

AUTHORITY:
Manual moon set → INVALID; refuse; require date change via CALENDAR.
TIME_STATE change ≠ moon change. Only CALENDAR date change re-derives moon.

IF CALENDAR date missing/ambiguous → NO_MOON_UPDATE; ask for date; MUST NOT guess.
INVALID if derived from TIME_STATE, “night”, narration, pacing, or travel without an explicit CALENDAR date change.
INVALID to use astronomy/real lunar timing/variable month length; only the closed table mapping is allowed.
INVALID if: manual set; implicit phase advance; mapping outside table; non-CALENDAR derivation.

FX+ (fiction only): ambience/light; superstition; ritual timing only if separate rules.
FX- (never): numeric modifiers, DC changes, conditions, forced outcomes.
