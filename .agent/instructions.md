# Antigravity Agentic Protocol

## Configuration

| Key | Value |
|-----|-------|
| **Skills Repo** | https://github.com/rmyndharis/antigravity-skills |
| **Catalog URL** | https://raw.githubusercontent.com/rmyndharis/antigravity-skills/main/catalog.json |
| **Bundles URL** | https://raw.githubusercontent.com/rmyndharis/antigravity-skills/main/bundles.json |
| **Skills Base** | https://raw.githubusercontent.com/rmyndharis/antigravity-skills/main/skills/ |

---

## Phase 0: Pack Discovery

### Step 1: PRD Check
- Look for `prd.md` in project root
- If missing → run `/prd-builder` workflow first
- Do NOT proceed without a PRD

### Step 2: Fetch Catalog
- Download `catalog.json` from GitHub (contains 300+ skills with triggers/tags)
- Download `bundles.json` for pre-grouped skill sets
- Parse and cache in memory

### Step 3: Skill Matching
Extract from PRD:
- **Technologies**: frameworks, languages, databases mentioned
- **Patterns**: authentication, api, testing, deployment, etc.
- **Keywords**: any domain-specific terms

Match against:
- Skill `triggers` array (primary match)
- Skill `tags` array (secondary match)
- Bundle groups for comprehensive coverage

**Mandatory Skills** (always include):
- `c4-architecture`
- `architecture-decision-records`

### Step 4: Materialize Skills
For each matched skill:
1. Download from: `{Skills Base}/{skill.path}`
2. Save to: `.agent/skills/{skill-id}.md`
3. Log skill name and description

### Step 5: Update State
Update `project-state.json`:
```json
{
  "active_skills": ["skill-id-1", "skill-id-2"],
  "current_phase": 0,
  "last_catalog_fetch": "ISO-date"
}
```

### Step 6: Generate Context
Create/update `.agent/project-context.md` with:
- PRD summary
- List of active skills
- Initial constraints

---

## Phase 1: Project Roadmap

After Pack Discovery completes:

1. **Analyze PRD** for logical phases:
   - MVP features → Phase 1
   - Core enhancements → Phase 2
   - Nice-to-haves → Phase 3+

2. **Generate `roadmap.md`** with:
   - Numbered phases with clear goals
   - Deliverables per phase
   - Skills mapped to each phase
   - Success criteria

3. **Update state**: Set `current_phase: 1`

---

## Phase 2+: Implementation

For each roadmap phase:

1. Create `implementation_plan.md` for the phase
2. Reference relevant skills from `.agent/skills/`
3. Execute with full context from `project-context.md`
4. Update `project-context.md` after major decisions
5. Create ADRs for significant architectural choices
6. Mark phase complete, increment `current_phase`

---

## Custom Skills

Skills from non-official repos require vetting:

1. Run `/skill-preview` workflow
2. Display skill content for review
3. Check for security concerns
4. Require explicit user approval
5. Mark as `"source": "custom"` in state
