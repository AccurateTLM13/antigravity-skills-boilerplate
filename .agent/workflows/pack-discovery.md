---
description: Initialize Phase 0 Pack Discovery - fetches skills from GitHub and matches to project needs
---

# Pack Discovery Workflow

Invoke with `/pack-discovery` to begin the Antigravity agentic setup.

## Prerequisites
- Project cloned from boilerplate (or `.agent/` structure added)
- `prd.md` in project root (or will run `/prd-builder` first)

---

## Steps

### 1. Verify PRD Exists
// turbo
Check for `prd.md` in project root.

**If missing**: 
- Notify user: "No PRD found. Running /prd-builder to create one."
- Execute `/prd-builder` workflow
- Return here after PRD is complete

### 2. Fetch Skill Catalog
// turbo
Download from GitHub:
```
Catalog: https://raw.githubusercontent.com/rmyndharis/antigravity-skills/main/catalog.json
Bundles: https://raw.githubusercontent.com/rmyndharis/antigravity-skills/main/bundles.json
```

Parse JSON and extract skill metadata.

### 3. Analyze PRD
// turbo
Extract keywords from `prd.md`:
- **Technologies**: React, Python, PostgreSQL, Kubernetes, etc.
- **Patterns**: authentication, API, testing, deployment, CI/CD
- **Domains**: e-commerce, healthcare, fintech, etc.

### 4. Match Skills
// turbo
For each skill in catalog:
1. Check if any PRD keyword matches skill `triggers` array
2. Check if any PRD keyword matches skill `tags` array
3. Consider relevant bundles for comprehensive coverage

**Always include**:
- `c4-architecture`
- `architecture-decision-records`

### 5. Download Matched Skills
// turbo
For each matched skill:
```
URL: https://raw.githubusercontent.com/rmyndharis/antigravity-skills/main/{skill.path}
Save: .agent/skills/{skill-id}.md
```

Report progress: "Downloaded: {skill-name} - {description}"

### 6. Update Project State
// turbo
Update `.agent/project-state.json`:
```json
{
  "skills_repo": "https://github.com/rmyndharis/antigravity-skills",
  "active_skills": ["skill-1", "skill-2", "..."],
  "current_phase": 0,
  "last_catalog_fetch": "2026-01-29T..."
}
```

### 7. Create Project Context
// turbo
Generate/update `.agent/project-context.md` with:
- PRD summary (first 2-3 sentences)
- List of active skills with one-line descriptions
- Current phase: 0 (Pack Discovery)

### 8. Generate Roadmap
Invoke `/roadmap-generator` to create project phases.

---

## Completion

After all steps:
1. Notify user: "Pack Discovery complete. X skills materialized."
2. Present list of matched skills
3. Show roadmap summary
4. Await approval to begin Phase 1
