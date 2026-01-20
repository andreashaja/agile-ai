---
description: Complete Phase 2, validate quality, and generate artifacts.
agent: architect
---

Execute the **Architecture Completion Routine**.

**CRITICAL:** Only the User may call this command. If you (the agent) think it's time to complete, SUGGEST it to the user but do NOT execute this yourself.

---

**Step 1: Validate Protocol Completeness**
Read `agile/artifacts/02_structure/ARCHITECT_PROTOCOL.md` and verify:
- [ ] Step 1 (ANALYZE) is marked complete with user confirmation
- [ ] Step 2 (DECIDE) is marked complete with user confirmation
- [ ] Step 3 (REFINE) is marked complete with user confirmation
- [ ] Step 4 (DEFINE) is marked complete with user confirmation
- [ ] Step 5 (PLAN) is marked complete with user confirmation

If ANY step is incomplete, inform the user which steps need attention.

**Step 2: Validate Content**
Check that we have all necessary information:
- [ ] User's technical level is documented
- [ ] Tech stack is decided and documented
- [ ] Technical stories have been added to backlog (with [TECH-ENABLER] tags)
- [ ] Definition of Done criteria are defined
- [ ] Sprint/execution plan exists
- [ ] No "TBD" or placeholder text remains

If anything is missing, inform the user and suggest completing that section first.

**Step 3: Read Templates**
Read the templates for output formatting:
- `agile/templates/02_structure/PROJECT_VISION_TEMPLATE.md` (if exists)
- `agile/templates/02_structure/PRODUCT_BACKLOG_TEMPLATE.md` (if exists)
- `agile/templates/02_structure/DEFINITION_OF_DONE_TEMPLATE.md`

**Step 4: Generate Artifacts**

1. **PROJECT_VISION.md (v2)**
   - Copy the Phase 1 vision as base
   - Add a new section "## Technical Architecture" with:
     - Technology stack decisions
     - Architecture overview
     - Key technical decisions and rationales

2. **PRODUCT_BACKLOG.md (v2)**
   - Copy the Phase 1 backlog as base
   - Integrate all `[TECH-ENABLER]` and `[ARCH-ADD]` stories
   - Add priority markers (High/Medium/Low or Sprint assignments)
   - Preserve ALL original user stories (never delete!)

3. **DEFINITION_OF_DONE.md**
   - Create from the agreed quality standards
   - Include all categories: Code Quality, Testing, Documentation, Deployment

Write all files to `agile/artifacts/02_structure/`.

**Step 5: Update Logs**
- Mark all todos as complete
- Update `AGENT_LOG.md` with completion timestamp
- Update `ARCHITECT_PROTOCOL.md` with handover summary

**Step 6: Verify & Announce**
List the generated files and announce:

> "Phase 2 is complete! I've generated:
> - PROJECT_VISION.md (v2) - now includes technical architecture
> - PRODUCT_BACKLOG.md (v2) - enhanced with technical tasks
> - DEFINITION_OF_DONE.md - our quality contract
>
> The project is ready for Phase 3 (Sprinter). When you're ready to start building, use `/sprinter-start`."
