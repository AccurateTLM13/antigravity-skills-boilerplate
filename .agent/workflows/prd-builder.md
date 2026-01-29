---
description: Interactive interview to build a Product Requirements Document when none exists
---

# PRD Builder Workflow

Invoke with `/prd-builder` when starting a new project without requirements.

## Interview Process

Ask these questions in sequence, waiting for each answer before proceeding:

### 1. Project Overview
- What is the project name?
- Describe the project in 1-2 sentences.

### 2. Target Users
- Who will use this? (developers, end-users, businesses, internal team)
- What problem does it solve for them?

### 3. Core Features (MVP)
- List 3-5 must-have features for the initial release.
- What is the absolute minimum needed to be useful?

### 4. Nice-to-Have Features
- What features could wait for later versions?
- Any stretch goals?

### 5. Technical Preferences
- Any preferred technologies? (frameworks, languages, databases)
- Any technologies to avoid or existing constraints?
- Will this integrate with existing systems?

### 6. Constraints
- Timeline expectations? (rough estimate is fine)
- Platform targets? (web, mobile, desktop, API-only)
- Any budget or resource limitations?
- Regulatory or compliance requirements?

### 7. Success Metrics
- How will you measure success?
- What does "done" look like for MVP?

---

## Output Format

Generate `prd.md` in project root with this structure:

```markdown
# [Project Name] - Product Requirements Document

## Overview
[1-2 sentence description from interview]

## Target Audience
- **Primary Users**: [who]
- **Problem Solved**: [what]

## Features

### MVP (Must Have)
- [ ] Feature 1
- [ ] Feature 2
- [ ] Feature 3

### Future (Nice to Have)
- [ ] Feature A
- [ ] Feature B

## Technical Requirements
- **Stack**: [preferences]
- **Platforms**: [targets]
- **Integrations**: [if any]
- **Constraints**: [avoid list]

## Constraints
- **Timeline**: [expectation]
- **Compliance**: [if any]

## Success Criteria
- [Metric 1]
- [Metric 2]
```

---

## After Completion

Once `prd.md` is generated:
1. Save to project root
2. Notify user to review
3. Proceed to Phase 0: Pack Discovery
