FA.SETTLEMENT.TOGGLE (LAW)
Region: Forest of Allanar.
Authority: CORE.GOVERNANCE.CORE.
Purpose: enforce single-active settlement invariant.

DEFINITION:
FA settlement unit = any active unit with UNIT_ID prefix FA.SETTLEMENT.*

INVARIANT (HARD):
VALID:
- 0 active FA settlements
- 1 active FA settlement
INVALID:
- 2+ active FA settlements

ON INVALID:
- HARD_STOP
- ERROR_CODE: FA_ERR_MULTI_SETTLEMENT_ACTIVE
- REPORT: list of all active FA.SETTLEMENT.* unit IDs
- INVALID to resolve by priority, guessing, or suppression

DERIVED OUTPUT (SOLE AUTHORITY):
FA_ACTIVE_SETTLEMENT =
- NULL if 0 active
- the single FA.SETTLEMENT.* UNIT_ID if exactly 1 active

CONSUMER REQUIREMENTS:
Any FA subsystem that depends on settlement context MUST:
- Read FA_ACTIVE_SETTLEMENT at execution time
- INVALID if using cached or inferred settlement
- If FA_ACTIVE_SETTLEMENT=NULL and settlement is required →
  HARD_STOP with ERROR_CODE: FA_ERR_NO_SETTLEMENT_SELECTED

PROHIBITIONS:
- No default settlement
- No fallback behavior
- No silent override
- No persistence of prior settlement context
