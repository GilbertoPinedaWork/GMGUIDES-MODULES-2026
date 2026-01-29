NPC.LAW.FA (LAW)
Region: Forest of Allanar.
Authority: NPC.LAW.CORE (supreme).
Function: FA-specific NPC validation and memory enforcement.

APPLIES_ONLY_IF:
FA=ON
INVALID to apply when FA=OFF.

CANONICAL LABEL (ONLY):
SETTLEMENT_BOUND_REGION_FA_<SETTLEMENT>
INVALID if any other label used for FA NPCs.

LABEL RULES:
GLOBAL_CANON → see NPC.LAW.CORE.
REGION_KNOWN_FA → name-only within FA; INVALID to act unless settlement active.
SETTLEMENT_BOUND_REGION_FA_<SETTLEMENT> →
- Act/update ONLY_IF that settlement is the active settlement.
- INVALID to update while dormant.
- INVALID to migrate without explicit declared transition.
SCENE_LOCAL → scene-only; auto-expire.
SECRET_HIDDEN → no reference/action until revealed.

MEMORY GOVERNANCE:
DEFAULT_MEMORY=NONE.
Persistence ONLY_IF player approval.
UNAPPROVED_UPDATE → INVALID.
NO_PLAYER_UPDATE → revert NPC to baseline.

MEMORY HANDOFF (MANDATORY & EXACT):
Only valid IF:
FA=ON AND
NPC_LABEL=SETTLEMENT_BOUND_REGION_FA_<ACTIVE_SETTLEMENT>

PROMPT (EXACT; no paraphrase):
<<Update NPC card of [NPC NAME] with Additional Information:
[brief summary of new facts, attitudes, promises, or changes]>>

HANDOFF TRIGGERS (CLOSED):
NEW_FACT
NPC_LEARNED_ABOUT_PC
PROMISE_THREAT_REQUEST
ATTITUDE_CHANGED
TASK_OR_OBLIGATION_CREATED_OR_RESOLVED

NO HANDOFF FOR:
FLAVOR_DIALOGUE
SMALL_TALK
REPEATED_INFO
NON_COMMITTAL

EXPRESSION:
Defer to GM behavior layer.

STATUS:
Binding regional constraint for Forest of Allanar.
