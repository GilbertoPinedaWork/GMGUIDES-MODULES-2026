CALENDAR (LAW)
Uniform calendar: 12 months/year, 30 days/month. No variation, no leap days.

DATE=(YEAR?, MONTH_INDEX, DAY)
YEAR optional; if omitted → internal YEAR=0 for computation only.

RANGES:
MONTH_INDEX∈{1..12}
DAY∈{1..30}
YEAR∈Z, YEAR>=0 (if present)

NO_IMPLICIT: date never changes by narration, travel, pacing, combat, fatigue, or tone.
INVALID if inferred from narration, travel distance, combat duration, pacing, fatigue, or tone.

AUTHORITY (only):
- PLAYER explicit request, or
- SYSTEM declaration with explicit delta or explicit target date.
NO_OTHER → INVALID; NO_DATE_CHANGE.

OPS:
SET_DATE(Y?,M,D)
ADD_DAYS(N>=0 integer)
SUBTRACT_DAYS(N>=0 integer)

IF request ambiguous or lacks explicit delta/target → NO_DATE_CHANGE; ask clarification; MUST NOT guess.

MATH:
ABS=(YEAR*360)+((MONTH_INDEX-1)*30)+(DAY-1)
if YEAR omitted → YEAR=0 for ABS only

ADD:
ABS2=ABS+N
YEAR2=ABS2//360
REM =ABS2%360
MONTH2=(REM//30)+1
DAY2  =(REM%30)+1

SUB:
ABS2=max(0,ABS-N)
derive as above

APPLY:
If YEAR tracked → update YEAR
If YEAR omitted → keep YEAR omitted in display

INTEGRATION:
DATE change ≠ TIME change.
DATE change → derive MOON immediately.

INVALID if:
- non-integer/negative/fractional N
- MONTH_INDEX or DAY out of range
- implicit date advance
- non-calendar derivation

FX- (never): real calendars, variable months, leap days, implicit advance.
