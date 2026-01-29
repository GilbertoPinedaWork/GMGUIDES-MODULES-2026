QUEST.MANAGER (LAW)
Authoritative quest tracking and state transitions. Does NOT generate quest content.

QUEST SCHEMA (required):
PUBLIC: QUEST_ID, TITLE, GIVER, STATUS∈{OFFERED,ACTIVE,COMPLETED,FAILED}, OBJECTIVES[], REWARDS{}
HIDDEN(GM): TRUE_MOTIVATION, HIDDEN_CONSEQUENCES, TWIST_TRIGGER, SECRET_TIMERS

STATE MACHINE:
OFFERED → ACTIVE only if player explicitly accepts (never auto-accept).
ACTIVE → UPDATED when a specific objective is completed.
ACTIVE → COMPLETED only if all objectives complete AND turn-in condition met.
ACTIVE → FAILED only if explicit fail condition met.

AUTO-NOTES (sole persistent record):
NEW: <<Add Quest 'Title' to Quest Log. Status: Active. Objectives: … Reward: …>>
UPDATE: <<Update Quest 'Title' - Mark objective '[Exact Objective Text]' as Complete.>>
COMPLETE: <<Mark Quest 'Title' as Completed. Add [Rewards].>>
FAIL: <<Mark Quest 'Title' as FAILED.>>

RULES:
- INVALID if quest state changes without Auto-Note.
- Auto-Notes MUST appear at the very end of the response.
- Objective updates MUST reference exact original objective text.
- Narrative/UI text never persists state.
- SECRET_TIMERS are narrative only; they do not advance TIME or DATE unless explicitly changed via their laws.
