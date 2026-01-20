# Definition of Done (DoD) - {{PROJECT_NAME}}

This document serves as our binding **Quality Contract**.
A User Story or Task is only considered "Done" when all relevant criteria in this list are met.

---

## 1. Code Quality & Hygiene
*Motivation: {{WHY_CODE_QUALITY_MATTERS}}*

*   [ ] **No Linting Errors:** The project must pass the standard linter check without warnings.
    *   *How to check:* Run `{{LINT_COMMAND}}`.
*   [ ] **Clean Formatting:** The code follows a consistent style.
    *   *How to check:* Run `{{FORMAT_COMMAND}}`.
*   [ ] **Descriptive Naming:** Variables and functions have clear, meaningful names.
*   [ ] **No "Dead" Code:** No commented-out blocks or forgotten debug statements.

## 2. Runtime Stability
*Motivation: {{WHY_STABILITY_MATTERS}}*

*   [ ] **Crash Resilient:** The application must handle unexpected input gracefully.
    *   *How to check:* {{STABILITY_TEST_INSTRUCTIONS}}
*   [ ] **Error Handling:** All errors are caught and logged appropriately.
*   [ ] **Environment Verified:** The feature must be tested in the target environment.

## 3. User Experience (UX)
*Motivation: {{WHY_UX_MATTERS}}*

*   [ ] {{UX_CRITERION_1}}
*   [ ] {{UX_CRITERION_2}}
*   [ ] {{UX_CRITERION_3}}

## 4. Documentation & Handover
*Motivation: We might forget how this works by tomorrow.*

*   [ ] **README Updated:** If this feature requires new installation steps, they must be documented.
*   [ ] **Code Comments:** Complex logic must be commented with "Why", not just "What".
*   [ ] **Helper Scripts:** Start/stop scripts are provided and tested.

## 5. Testing (if applicable)
*Motivation: {{WHY_TESTING_MATTERS}}*

*   [ ] **Unit Tests Pass:** Run `{{TEST_COMMAND}}`.
*   [ ] **Manual Testing:** Feature has been manually verified by the developer.

---

*Note: Not all criteria apply to every task. Mark N/A for irrelevant items.*
