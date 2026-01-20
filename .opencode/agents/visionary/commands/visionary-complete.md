---
description: Finish Phase 1, validate completeness, and generate artifacts.
agent: visionary
---

# /visionary-complete

Execute the **Vision Completion Routine**.

**IMPORTANT:** This command should only be called by the User after you have proposed completion in Step 5. If the User calls this prematurely, guide them back to the interview process.

---

## Pre-Completion Validation

Before generating artifacts, perform a final validation:

### 1. Protocol & Log Check

Read both log files and verify:

**INTERVIEW_PROTOCOL.md:**
- All 5 steps are marked as "Completed"
- No steps are still "Pending" or "In Progress"
- Conversation is documented (questions and answers present)

**AGENT_LOG.md:**
- All todo state transitions are logged
- All 5 steps show final state "completed"
- Completion checklist items can be checked off

If any step is incomplete, inform the User and guide them back to complete the missing step.

### 2. Structural Completeness Check

Verify the following (guidelines, not hard gates):

```
□ Product Goal exists (1-2 sentence Elevator Pitch)
□ Target Audience is defined
□ Scope boundaries documented (In-Scope AND Out-of-Scope)
□ Epics identified (recommended: 3-5)
□ Each Epic has a Business Value statement
□ Each Epic has User Stories (recommended: 3-5 per Epic)
□ Each Story follows "As a... I want... So that..." format
□ No open "TBD" or placeholder text
```

### 3. INVEST Quality Check

For EACH User Story, verify:

| Criterion | Question | Status |
|-----------|----------|--------|
| **I**ndependent | Can be implemented without depending on another story? | ✓/✗ |
| **N**egotiable | Leaves room for implementation decisions? | ✓/✗ |
| **V**aluable | Clear benefit to a user or stakeholder? | ✓/✗ |
| **E**stimable | Enough detail for a developer to estimate? | ✓/✗ |
| **S**mall | Small enough to complete in one sprint? | ✓/✗ |
| **T**estable | Clear criteria to verify completion? | ✓/✗ |

### 4. Consistency Check

- Are there contradictory requirements?
- Are all mentioned user roles represented in stories?
- Does the scope match the stories? (Nothing out-of-scope in backlog?)

---

## Decision Point

**If validation PASSES:**
Proceed to artifact generation.

**If validation FAILS:**
1. Report the specific issues found
2. Say: *"I found some gaps we should address before generating the documents: [list issues]. Let's resolve these first."*
3. Work with User to resolve issues
4. User can call `/visionary-complete` again when ready

---

## Artifact Generation

If validation passes, generate the artifacts:

### Step 1: Read Templates

Read the templates to ensure correct format:
- `agile/templates/01_vision/PROJECT_VISION_TEMPLATE.md`
- `agile/templates/01_vision/PRODUCT_BACKLOG_TEMPLATE.md`

Also reference the examples for quality standard:
- `agile/templates/01_vision/PROJECT_VISION_EXAMPLE.md`
- `agile/templates/01_vision/PRODUCT_BACKLOG_EXAMPLE.md`

### Step 2: Generate Files

Create the following files in `agile/artifacts/01_vision/`:

**PROJECT_VISION.md** containing:
- Elevator Pitch
- Business Goals
- Target Audience
- Scope (In/Out)
- Risk factors (if discussed)
- Epic Overview (titles and goals)

**PRODUCT_BACKLOG.md** containing:
- All Epics with Business Value
- All User Stories in proper format
- Acceptance Criteria where captured
- Priority grouping (High/Medium/Low or Icebox)

### Step 3: Update Both Log Files

**Update `agile/artifacts/01_vision/INTERVIEW_PROTOCOL.md`:**
- Change overall Status to "Completed"
- Add completion timestamp
- Add final artifact list
- Add summary statistics

**Update `agile/artifacts/01_vision/AGENT_LOG.md`:**
- Log final todo state change (all items → completed)
- Check off all items in Completion Checklist
- Add session end timestamp
- Add final decision: "Artifacts generated successfully"

### Step 4: Verify Generation

After writing:
1. List the files in `agile/artifacts/01_vision/` to confirm creation
2. Briefly summarize what was generated

### Step 5: Handover

Announce completion with:

```
---
## Phase 1 Complete

I have generated the Vision artifacts:
- `agile/artifacts/01_vision/PROJECT_VISION.md`
- `agile/artifacts/01_vision/PRODUCT_BACKLOG.md`
- `agile/artifacts/01_vision/INTERVIEW_PROTOCOL.md` (conversation record)
- `agile/artifacts/01_vision/AGENT_LOG.md` (todo/decision audit trail)

**Summary:**
- Product: [name]
- Epics: [count]
- User Stories: [count]
- All stories INVEST-validated: Yes
- All workflow steps completed: Yes (see AGENT_LOG.md)

**Next Step:**
You can now proceed to Phase 2 (Structure) by calling `/architect-start`.
The Architect will review these artifacts and add technical details.
---
```

---

## Quality Reminders

- **Write for humans:** The documents should be readable by non-technical stakeholders
- **Preserve User's voice:** Use the User's terminology, not technical jargon
- **Be complete but concise:** Include all captured information, but don't pad with filler
- **Mark uncertainty:** If something was ambiguous, note it rather than guessing
- **Two audit trails:** 
  - INTERVIEW_PROTOCOL.md = What was discussed (for the user)
  - AGENT_LOG.md = What the agent did (for debugging)
