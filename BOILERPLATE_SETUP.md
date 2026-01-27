Antigravity Agent: Boilerplate Setup InstructionsRole: Technical Architect / Automation SpecialistObjective: Initialize a new high-signal project workspace linked to the Global Skill Library.1. Environment ContextGlobal Warehouse Path: ~/Desktop/dev/antigravity-skillsProject Briefcase Path: ./.agent/skills2. Setup Phase (Automated Action Required)Please execute the following technical setup immediately:A. Directory StructureCreate the .agent/ directory at the project root.Create the .agent/skills/ directory (The Briefcase).Create a project-state.json file in .agent/ to track active packs.B. Protocol InitializationCreate .agent/instructions.md with the following content:# Phase 0: Pack Discovery Protocol

When the user prompts "Let's begin with Phase 0: Pack Discovery," follow these steps exactly:

## 1. Locate the Warehouse
- Path: `~/Desktop/dev/antigravity-skills/skills/`
- Catalog: `~/Desktop/dev/antigravity-skills/catalog.json`

## 2. Audit & Match
- **New Projects:** Analyze the provided PRD or intent. Extract 5-10 specific IDs from the Global Catalog.
- **Active Projects:** Scan the codebase (dependencies/files). Identify technologies used that lack a local SKILL.md.

## 3. Materialization
- Copy the matching `SKILL.md` files from the Warehouse to `./.agent/skills/`.
- **Mandatory Anchors:** Always include `c4-architecture` and `architecture-decision-records`.

## 4. Gap Detection
- If a required tech is missing from the Warehouse, research it and generate a new standard-compliant `SKILL.md` in `./.agent/skills/`. Flag for Global Export.
\```

### C. Rule Injection
1. Create or update `.clinerules` (or `.cursorrules`) in the project root.
2. Add this directive at the top:
   > "CRITICAL: Always read and follow the protocols in `./.agent/instructions.md` before initiating any workflow. Every project must start with 'Phase 0: Pack Discovery'."

---

## 3. The Seed
Copy the following core skills from the Warehouse to `.agent/skills/` right now:
- `~/Desktop/dev/antigravity-skills/skills/c4-architecture/SKILL.md` -> `.agent/skills/architecture.md`
- `~/Desktop/dev/antigravity-skills/skills/architecture-decision-records/SKILL.md` -> `.agent/skills/adr.md`

---

## 4. Verification
Once setup is complete, confirm by stating:
**"Antigravity Boilerplate Initialized. System core seeded. Standing by for Phase 0: Pack Discovery."**
