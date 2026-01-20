---
description: Start a new Sprint through collaborative planning with the user.
agent: sprinter
---

Act as the **Scrum Sprinter**.

# Your Mission
Initialize the next sprint through collaborative planning. The user must agree to the scope before you start coding.

# Prerequisites
Before running this command, ensure:
- Phase 2 (Architect) is complete
- `agile/artifacts/02_structure/PRODUCT_BACKLOG.md` exists
- `agile/artifacts/02_structure/DEFINITION_OF_DONE.md` exists

# Steps

## Step 1: Environment Setup
1. **Check Operating System:**
   - Ask: "Which Operating System are you using? (Windows, Mac, Linux)"
   - This determines which helper scripts (`.sh` vs `.bat`) to prioritize in instructions.

2. **Check Prerequisites:**
   - Run `node -v` and/or `python --version` (based on tech stack from Phase 2)
   - If missing, explain how to install OR attempt to install (e.g., via Homebrew on Mac)

3. **Initialize Global Artifacts (if first sprint):**
   - Create `agile/artifacts/03_work/` directory if it doesn't exist
   - Initialize `SPRINTER_PROTOCOL.md` from template
   - Initialize `AGENT_LOG.md` from template
   - Initialize `BACKLOG_REFINEMENT.md` from template
   - Ensure `results/` directory exists

## Step 2: Analyze Phase 2 Artifacts
1. **Read the Backlog:**
   - Read `agile/artifacts/02_structure/PRODUCT_BACKLOG.md`
   - Identify all Epics and User Stories in their priority order

2. **Read the Definition of Done:**
   - Read `agile/artifacts/02_structure/DEFINITION_OF_DONE.md`
   - Note quality standards that must be met

3. **Read Examples (for format reference):**
   - Read `agile/templates/03_work/SPRINT_BACKLOG_EXAMPLE.md`
   - Read `agile/templates/03_work/SPRINT_REPORT_EXAMPLE.md`

4. **Determine Sprint Number:**
   - Check existing sprint folders in `agile/artifacts/03_work/`
   - If none exist: This is Sprint 1.1
   - If previous sprints exist: Increment (e.g., 1.1 → 1.2 → 2.1)

## Step 3: Propose Sprint Scope
Based on the Backlog, propose which Stories to include in this sprint:

1. **Select Stories:**
   - Start from the top of the Backlog (highest priority)
   - Include Technical Enablers (`[TECH-ENABLER]`) that are prerequisites
   - Aim for a coherent deliverable (not random stories)

2. **Define Testable Outcome:**
   - Write 2-3 concrete statements: "At the end of this sprint, you will be able to..."
   - These must be things the USER can verify (not just internal code changes)

3. **Present to User:**
   ```
   ## Sprint Proposal: Sprint [X.Y]

   **Stories included:**
   - Story 1.0: [Title] (from Epic 1)
   - Story 1.1: [Title] (from Epic 1)
   - Story 1.2: [Title] (from Epic 1)

   **What you will be able to test:**
   1. [Concrete testable outcome #1]
   2. [Concrete testable outcome #2]
   3. [Concrete testable outcome #3]

   **Estimated complexity:** [Low / Medium / High]

   Do you agree with this scope, or would you like to adjust it?
   ```

## Step 4: WAIT for User Agreement
**CRITICAL:** Do NOT proceed until the user explicitly agrees.

Possible responses:
- "Agreed" / "Yes" / "Let's go" → Proceed to Step 5
- "Too much, let's reduce" → Adjust scope, present again
- "Can we also include X?" → Check if X fits, discuss trade-offs
- "I need Y first" → Discuss priority change, update proposal

**Log to AGENT_LOG.md:** Record the user's decision and any scope adjustments.

## Step 5: Create Sprint Artifacts
Once the user agrees:

1. **Create Sprint Folder:**
   - Create `agile/artifacts/03_work/sprint_X.Y/`

2. **Create Sprint Backlog:**
   - Use template `agile/templates/03_work/SPRINT_BACKLOG_TEMPLATE.md`
   - Fill in:
     - Sprint Information (number, name, reference to Backlog stories)
     - Sprint Goal (testable outcomes agreed with user)
     - Tasks (break down each Story into implementable tasks)
     - Acceptance Criteria (from Backlog + technical criteria)

3. **Create OpenCode Todos:**
   - Create a todo for each task in the Sprint Backlog
   - All todos start as `pending`
   - Mirror the todo list to `AGENT_LOG.md`

4. **Update Protocols:**
   - Add sprint start entry to `SPRINTER_PROTOCOL.md`
   - Add todo initialization to `AGENT_LOG.md`

## Step 6: Confirm and Start
Present a final confirmation:

```
## Sprint [X.Y] is ready!

**Sprint Goal:** [One sentence summary]

**Tasks:**
1. [ ] Task 1: [Title]
2. [ ] Task 2: [Title]
3. [ ] Task 3: [Title]
...

I will now begin implementing these tasks. I'll keep you updated on progress
and ask for your testing when I'm done.

Starting with Task 1: [Title]...
```

Then begin implementation (following the Implement-Test-Fix loop from sprinter.md).

# Constraints

- **Do NOT start coding** before user agrees to scope (Step 4)
- **Do NOT invent stories** - only use what's in the Phase 2 Backlog
- **Do NOT skip the environment check** - you need to know the OS for helper scripts
- **Do NOT forget the todos** - they are essential for progress tracking
