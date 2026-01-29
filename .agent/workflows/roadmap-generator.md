---
description: Generate a phased project roadmap from completed PRD
---

# Roadmap Generator Workflow

Invoke with `/roadmap-generator` after Pack Discovery completes.

## Prerequisites
- `prd.md` exists in project root
- Pack Discovery has materialized skills to `.agent/skills/`

---

## Process

### 1. Analyze PRD

Extract and categorize:

| Category | Maps To |
|----------|---------|
| MVP features | Phase 1 |
| Core enhancements | Phase 2 |
| Nice-to-haves | Phase 3+ |
| Polish/optimization | Final phase |

### 2. Map Skills to Phases

For each phase, identify which skills from `.agent/skills/` are relevant:
- Architecture skills → Early phases
- Testing skills → Every phase
- Deployment skills → Later phases
- Domain-specific → As needed

### 3. Define Milestones

Each phase needs:
- Clear goal statement
- Specific deliverables (as checklist)
- Success criteria (how to verify done)
- Estimated complexity (S/M/L)

---

## Output Format

Generate `roadmap.md` in project root:

```markdown
# [Project Name] Roadmap

Generated: [date]
Based on: prd.md

---

## Phase 1: MVP
**Goal**: [Core value proposition working]
**Complexity**: [S/M/L]

### Deliverables
- [ ] Deliverable 1
- [ ] Deliverable 2

### Skills Required
- `c4-architecture` - System design
- `[matched-skill]` - [purpose]

### Success Criteria
- [ ] Criteria 1
- [ ] Criteria 2

---

## Phase 2: [Name]
**Goal**: [What this phase achieves]
**Complexity**: [S/M/L]

### Deliverables
- [ ] ...

### Skills Required
- ...

### Success Criteria
- [ ] ...

---

## Phase 3: [Name]
...
```

---

## After Completion

1. Save `roadmap.md` to project root
2. Update `project-state.json`: set `current_phase: 1`
3. Update `project-context.md` with roadmap summary
4. Notify user roadmap is ready for review
5. Await approval before starting Phase 1 implementation
