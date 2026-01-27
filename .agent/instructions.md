# Phase 0: Pack Discovery Protocol

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
