---
description: Initialize Phase 0 Pack Discovery in any project - copies the Antigravity boilerplate structure and begins skill matching
---

# Pack Discovery Workflow

Use this workflow to bootstrap the Antigravity agentic system in **any project**.

## Prerequisites
- Antigravity Skills Warehouse cloned at `~/Desktop/dev/antigravity-skills/`
- This boilerplate repository available (local or cloned)

---

## Steps

### 1. Copy Boilerplate Structure to Target Project
// turbo
```bash
# From your target project root, copy the .agent folder structure:
xcopy /E /I "<boilerplate-path>\.agent" ".\.agent"
copy "<boilerplate-path>\.clinerules" ".\.clinerules"
```

> [!NOTE]
> Replace `<boilerplate-path>` with the actual path to this boilerplate (e.g., `C:\Users\JP\Desktop\antigravity-skills-boilerplate`)

### 2. Verify Structure
// turbo
Confirm these files exist in your project root:
```
your-project/
├── .agent/
│   ├── instructions.md        # Phase 0 Protocol
│   ├── skills/                # Local skill briefcase
│   │   ├── architecture.md    # C4 Architecture (pre-seeded)
│   │   └── adr.md             # ADR skill (pre-seeded)
│   └── project-state.json     # Skill tracking
├── .clinerules                # Agent behavior rules
└── (your project files)
```

### 3. Begin Pack Discovery
Now trigger the protocol by saying:
> "Let's begin with Phase 0: Pack Discovery"

The agent will:
1. **Locate Warehouse** at `~/Desktop/dev/antigravity-skills/`
2. **Audit & Match** - Analyze your PRD or codebase for required skills
3. **Materialize** - Copy matching `SKILL.md` files to `.agent/skills/`
4. **Gap Detection** - Flag missing skills for creation

### 4. Provide Context (if new project)
If starting fresh, provide:
- A `prd.md` (Product Requirements Document), OR
- A description of technologies and goals

The agent will extract 5-10 skill IDs from the Global Catalog to match your needs.

---

## Quick One-Liner (PowerShell)

For fast setup, run from your target project root:

```powershell
$boilerplate = "C:\Users\JP\Desktop\antigravity-skills-boilerplate"
xcopy /E /I "$boilerplate\.agent" ".\.agent"; copy "$boilerplate\.clinerules" ".\.clinerules"
```

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Agent doesn't see skills | Ensure `.agent/` is at project **root**, not nested |
| Warehouse not found | Verify `~/Desktop/dev/antigravity-skills/` exists |
| Skills not copying | Check file permissions on target directory |
