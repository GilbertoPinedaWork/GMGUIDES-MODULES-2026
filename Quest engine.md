QUEST.GEN (ENGINE LAW) v2.1
MODE: ON_DEMAND. DEFAULT=OFF. Purpose: instantiate ONE new Quest instance only. Tracking/updating/completion handled by QUEST.MANAGER.

ACTIVATE ONLY IF (no random quests):
A) Player explicitly solicits work/rumors/opportunity from NPC.
B) Narrative bridge needed to move PCs to target location/entity.
C) Faction gate: renown threshold triggers offer/test/promotion task.
If no valid trigger or trigger ambiguous → ENGINE OFF; generate nothing; ask clarification.

REQUIRES: QUEST.MANAGER + WORLD.REGION.CONTROL + CORE.AFFILIATION.GLOBAL. Must respect WORLD.CANON.
ANTI-DRIFT: NO_HYBRIDIZATION (engine creates; manager tracks). NO_TIER_JUMPING.

STEP 1 LOCATION (by settlement type):
- WILDS: survival, monster hunting, ruins exploration
- HAMLET/VILLAGE: gathering, local defense, disputes, agricultural threats
  PROHIBITED: world-ending threats; planar travel
- TOWN: trade protection, low-level organized crime, guild tasks
- CITY/METROPOLIS: intrigue, arcane mysteries, high-stakes heists, faction warfare

STEP 2 TIER (by APL):
T1 APL 1–4
T2 APL 5–10
T3 APL 11–16
T4 APL 17–20
INVALID if quest tier != APL tier.

DC TABLE (closed; choose one band only):
T1: DC 10–15
T2: DC 14–20
T3: DC 18–25
T4: DC 22–30+
Rule: Use DC from the tier’s band only; do not invent out-of-band DC.

STEP 3 AFFILIATION (CORE.AFFILIATION.GLOBAL):
- Infamous/Notorious: legal quests locked; underworld unlocked
- Enemy/Rival: refuse or trap
- Neutral/Fair: basic contract work
- Trusted/Ally: sensitive internal missions, leadership tasks

STEP 4 TEMPLATE (choose exactly one; weights optional):
SHORT (single goal; ~1 scene)
ARC (multi-stage; regional span)
PERSONAL (tied to PC traits; reward may be unique feature/feat)

STEP 5 REWARDS (closed tables; pick one entry per category)

XP (completion) TABLE (closed):
MINOR: 50
STANDARD: 100–250
MAJOR_ARC: 500

XP (combat) TABLE (closed guidance):
CR 1/4 → 50 XP  (low baseline)
CR 3+  → 700+ XP (high baseline)
Rule: combat XP is guidance only; do not force outcomes; do not exceed tier plausibility.

GOLD TABLE (closed by settlement type; respects original bands):
VILLAGE: 10–50
TOWN: 50–200
CITY: 200+
To avoid numeric drift, apply a tier cap to CITY:
- T1 CITY cap: 200–400
- T2 CITY cap: 200–800
- T3 CITY cap: 200–1500
- T4 CITY cap: 200–3000
Rule: If CITY reward chosen, it MUST fall within the tier cap above.

OUTPUT SCHEMA:
SURFACE: Title; Hook; Stated Reward.
SHADOW (GM-only): True Motivation; Twist Trigger; Secret Timer.
MECHANICS: Primary Skill; Challenge Rating only if violence occurs.

TIMER RULE (hard):
Secret Timer is narrative only. It does not advance TIME or DATE unless TIME/DATE are explicitly changed via their laws.

HANDOFF:
1) Present via NPC dialogue.
2) Ask acceptance (do not auto-accept).
3) Log via QUEST.MANAGER auto-note syntax.
4) After logging ONE quest instance → ENGINE OFF immediately. No further quest generation unless re-triggered explicitly.

INVALID IF ANY:
- random quest generation (no trigger)
- more than one quest generated per activation
- planar/world-ending quest in hamlet/village
- tier mismatch or tier jumping
- DC outside tier band
- rewards outside settlement band or CITY tier cap
- using Secret Timer to implicitly advance TIME/DATE
