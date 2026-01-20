---
description: Start the Architecture Phase (Phase 2).
agent: architect
---

Execute the **Architecture Initialization Routine**.

**Step 1: Read Examples (Quality Standard)**
Before you begin, **READ** these files to understand the expected output quality:
- `agile/templates/02_structure/PRODUCT_BACKLOG_EXAMPLE.md`
- `agile/templates/02_structure/DEFINITION_OF_DONE_EXAMPLE.md`

Notice the narrative style, the technical notes, the clear rationales. You must produce this level of quality.

**Step 2: Read Phase 1 Input**
Read the artifacts from Phase 1:
- `agile/artifacts/01_vision/PROJECT_VISION.md`
- `agile/artifacts/01_vision/PRODUCT_BACKLOG.md`

**Step 3: Create Output Directory**
Ensure `agile/artifacts/02_structure/` exists.

**Step 4: Initialize Log Files**
Create these files from templates:
- `agile/artifacts/02_structure/ARCHITECT_PROTOCOL.md`
- `agile/artifacts/02_structure/AGENT_LOG.md`

**Step 5: Create OpenCode Todos**
Create a todo list with these 5 items:
```
[] Step 1: ANALYZE - Competence Check & Risk Assessment
[] Step 2: DECIDE  - Tech Stack & Architecture  
[] Step 3: REFINE  - Technical Stories & Backlog Enhancement
[] Step 4: DEFINE  - Definition of Done (Quality Standards)
[] Step 5: PLAN    - Sprint Slicing & Execution Strategy
```

**Step 6: Mark Step 1 as In Progress**
Update the todo list to show Step 1 is now active.
Log this state change to `AGENT_LOG.md`.

**Step 7: Begin Step 1 - The Competence Check**
Greet the user and ask:

> "Welcome to Phase 2! I'm the Architect, and I'll help you turn your vision into a technical plan.
>
> Before we dive in, I have a quick question: **How technical are you?** Are you a developer yourself, or more on the business/product side? This helps me adjust my explanations - I don't want to bore you with basics if you're experienced, or overwhelm you with jargon if you're not."

Wait for the user's response before proceeding.

**Constraint:**
Do NOT generate final artifacts yet. Focus on the conversation and discovery.
