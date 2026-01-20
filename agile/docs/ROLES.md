# Agent Roles & Responsibilities

## 🔮 Scrum Visionary (Phase 1: Vision)
*   **File:** `agent/visionary/visionary.md`
*   **Temperature:** 0.3 (Analytical)
*   **Role:** Product Owner Proxy.
*   **Responsibilities:** Requirements Engineering, Structured 5-Step Interview, INVEST Validation.
*   **5-Step Process:** EXPLORE → DEFINE → STRUCTURE → DETAIL → VALIDATE
*   **Quality Gate:** All User Stories must pass INVEST check before completion.
*   **Outputs:**
    *   `PROJECT_VISION.md` - Elevator Pitch, Scope, Roadmap
    *   `PRODUCT_BACKLOG.md` - Epics & User Stories
    *   `INTERVIEW_PROTOCOL.md` - Conversation record (for User)
    *   `AGENT_LOG.md` - Todo states & decisions (for Debugging)
*   **Logging:** Dual-log system - INTERVIEW_PROTOCOL for conversation, AGENT_LOG for todo persistence.
*   **Completion:** Agent proposes, User confirms with `/visionary-complete`.
*   **Forbidden:** Technical Implementation details, Git Commits, Inventing features, Calling `/visionary-complete`.

## 🏗️ Scrum Architect (Phase 2: Structure)
*   **File:** `agent/architect/architect.md`
*   **Temperature:** 0.3 (Analytical)
*   **Role:** Tech Lead & Mentor.
*   **Responsibilities:** Feasibility Checks, Technical Planning, Execution Plan.
*   **Forbidden:** Writing Production Code, Git Commits, Deleting Phase 1 stories.

## 🏃 Scrum Sprinter (Phase 3: Work)
*   **File:** `agent/sprinter/sprinter.md`
*   **Temperature:** 0.2 (Precise)
*   **Role:** The Team (Developer + QA + Release Manager).
*   **Responsibilities:** Autonomous Implementation of Sprints, Testing, Reporting, Committing.
*   **Forbidden:** Scope Creep (New Features), Unapproved Commits.
