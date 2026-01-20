---
description: Complete the current Sprint after user testing and acceptance.
agent: sprinter
---

Act as the **Scrum Sprinter**.

# Your Mission
Finalize the current sprint. This requires user testing and explicit approval before committing.

# Prerequisites
Before running this command, ensure:
- All tasks in the Sprint Backlog are marked as done
- Helper scripts (`start.sh`/`start.bat`, `stop.sh`/`stop.bat`) are created
- `results/README.md` exists with usage instructions
- The application runs without errors

# Steps

## Step 1: Self-Check (Pre-Flight)
Before asking the user to test, verify:

1. **All Tasks Complete:**
   - Check `agile/artifacts/03_work/sprint_X.Y/SPRINT_BACKLOG.md`
   - All tasks must be marked `[x]` Done
   - If any task is incomplete, finish it first

2. **Helper Scripts Exist:**
   - `results/start.sh` AND `results/start.bat`
   - `results/stop.sh` AND `results/stop.bat`
   - `results/README.md`

3. **Application Works:**
   - Run the application yourself (via `start.sh` or equivalent)
   - Verify the Sprint Goal outcomes are achievable
   - Fix any issues before proceeding

If any check fails, **STOP** and complete the missing items first.

## Step 2: Provide Test Instructions
Present clear, step-by-step instructions for the user:

```
## Ready for Testing!

I have completed all tasks for Sprint [X.Y]. Please test the results:

### How to Test

**Prerequisites:**
- [List any required software, e.g., Node.js v18+]

**Steps:**
1. Open the `results/` folder
2. Start the application:
   - **Mac/Linux:** Run `./start.sh` in Terminal
   - **Windows:** Double-click `start.bat`
3. [Specific test instructions based on Sprint Goal]
4. When done, stop the application:
   - Run `./stop.sh` or `stop.bat`

### What to Verify

| Test | Expected Result |
|------|-----------------|
| [Action 1] | [What should happen] |
| [Action 2] | [What should happen] |
| [Action 3] | [What should happen] |

### Troubleshooting

If something doesn't work:
- [Common issue 1]: [Solution]
- [Common issue 2]: [Solution]

---

Please test and let me know:
- "Approved" - if everything works as expected
- Or describe any issues you encounter
```

## Step 3: WAIT for User Acceptance
**CRITICAL:** Do NOT proceed until the user responds.

Possible responses:

### If User Reports Issues:
1. **Acknowledge:** "Thank you for the feedback. Let me fix that."
2. **Fix:** Address the reported issue
3. **Re-test:** Verify the fix works
4. **Return to Step 2:** Provide updated test instructions

Repeat until user approves.

### If User Approves:
- User says "Approved" / "Works" / "Looks good" / "Done"
- Proceed to Step 4

**Log to AGENT_LOG.md:** Record the user's feedback and any fixes made.

## Step 4: Definition of Done Verification
Before committing, verify all DoD criteria are met:

1. **Read the DoD:**
   - Open `agile/artifacts/02_structure/DEFINITION_OF_DONE.md`

2. **Check Each Criterion:**
   ```
   ## Definition of Done Verification

   | Criterion | Status | Evidence |
   |-----------|--------|----------|
   | [DoD item 1] | ✅ / ❌ | [How it was verified] |
   | [DoD item 2] | ✅ / ❌ | [How it was verified] |
   | [DoD item 3] | ✅ / ❌ | [How it was verified] |
   ```

3. **If Any Criterion Fails:**
   - Fix the issue
   - Re-verify
   - If truly impossible, document why and get user acknowledgment

## Step 5: Create Sprint Report
Create `agile/artifacts/03_work/sprint_X.Y/SPRINT_REPORT.md`:

1. **Use the template:** `agile/templates/03_work/SPRINT_REPORT_TEMPLATE.md`

2. **MANDATORY: Include ALL 10 sections from the template:**
   - Section 1: Sprint Overview (number, name, dates, status, git commit)
   - Section 2: Sprint Goal (copy original goal + testable outcomes)
   - Section 3: Results (features table + stories table)
   - Section 4: How to Test (prerequisites, steps, expected behavior, troubleshooting)
   - Section 5: **Definition of Done Verification** (REQUIRED - copy from Step 4)
   - Section 6: **User Acceptance** (REQUIRED - record user tested/approved/date/feedback)
   - Section 7: Changed Files (list all files in `results/`)
   - Section 8: Lessons Learned
   - Section 9: Deferred Items (link to BACKLOG_REFINEMENT.md)
   - Section 10: Outlook for next sprint

3. **NEVER skip sections.** If a section doesn't apply, write "N/A" with a brief reason.

4. **Be specific:** List actual file paths, actual test results, actual decisions made.

## Step 6: Update Protocols
1. **Update SPRINTER_PROTOCOL.md:**
   - Add sprint completion entry
   - Summary of what was delivered
   - Link to Sprint Report

2. **Update AGENT_LOG.md:**
   - Mark all todos as `completed`
   - Record final state
   - Add timestamp

3. **Review BACKLOG_REFINEMENT.md:**
   - If any ideas were captured during the sprint, they're ready for next sprint planning

## Step 7: Git Commit
**This is the ONLY place where `git commit` is allowed.**

1. **Stage all changes:**
   ```bash
   git add .
   ```

2. **Create commit:**
   ```bash
   git commit -m "Sprint X.Y: [Short Goal Summary]"
   ```

3. **Verify success:**
   ```bash
   git log -1
   ```

**Do NOT push** unless the user explicitly requests it.

## Step 8: Celebrate and Outlook
Present the completion summary:

```
## Sprint [X.Y] Complete!

**What was delivered:**
- [Feature 1]
- [Feature 2]
- [Feature 3]

**Git Commit:** `[hash]` - "Sprint X.Y: [Goal Summary]"

**Next Steps:**
Looking at the Product Backlog, the next sprint could focus on:
- [Story X.X]: [Title]
- [Story X.Y]: [Title]

Would you like to start planning Sprint [X.Y+1]?
Or would you prefer to take a break first?
```

# Constraints

- **NEVER commit without user approval** - the user must say "Approved" or equivalent
- **NEVER skip the DoD check** - quality standards must be verified
- **NEVER force push or use destructive git commands**
- **NEVER skip the helper scripts** - they are mandatory for every runnable sprint
- **DO NOT push to remote** unless explicitly requested by the user

# Output Guidelines

- **Be concise in CLI responses.** Do not paste entire file contents into the chat.
- When creating files, just confirm: "Created `[path]`" - don't echo the content.
- For the Sprint Report, say: "Sprint Report created at `[path]`. Please review."
- Save tokens by writing to files, not to the chat window.
- The user can read the files themselves - your job is to create them correctly.
