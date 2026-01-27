# Antigravity Skills Boilerplate

**High-Signal Agentic Workflow Starter Kit**

This repository provides the foundational structure for enabling Antigravity Agentic workflows in any project. It includes "Skills" (modular context packs) and protocols that AI agents automatically follow.

## Prerequisites

> [!IMPORTANT]
> This boilerplate relies on a local "Global Warehouse" of skills.

Ensure you have the **Antigravity Skills** repository cloned to:

```
~/Desktop/dev/antigravity-skills
```

## Quick Start

There are **two ways** to use this boilerplate:

### Option A: Clone as New Project (Fresh Start)

```bash
git clone https://github.com/AccurateTLM13/antigravity-skills-boilerplate.git my-new-project
cd my-new-project
rm -rf .git && git init  # Fresh git history
```

Then trigger with: **"Let's begin with Phase 0: Pack Discovery"**

### Option B: Add to Existing Project (Recommended)

Use the `/pack-discovery` workflow to copy the structure into any existing project:

```powershell
# From your target project root:
$boilerplate = "C:\Users\JP\Desktop\antigravity-skills-boilerplate"
xcopy /E /I "$boilerplate\.agent" ".\.agent"
copy "$boilerplate\.clinerules" ".\.clinerules"
```

Or invoke the workflow by saying: **"/pack-discovery"**

> [!CAUTION]
> The `.agent/` folder **must be at your project root** for agents to discover it. Nested boilerplate folders won't work.

## Repository Structure

- **`.agent/`**: Contains the brain of the project.
    - **`workflows/`**: Reusable automation workflows (invoke with `/workflow-name`)
    - **`skills/`**: The local "Briefcase" where project-specific skills are copied to.
    - **`instructions.md`**: The detailed protocols the agent follows.
    - **`project-state.json`**: Tracks the active skills in the project.
- **`.clinerules`**: System instructions ensuring the agent follows the Antigravity protocols and prioritizes "Phase 0".

## Included Core Skills

By default, this boilerplate comes seeded with two mandatory anchors:
- **C4 Architecture**: for documenting system context and containers.
- **ADR (Architecture Decision Records)**: for tracking significant architectural decisions.
