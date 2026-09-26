# 05 — Clean Refactoring

**Role in the pipeline:** Architectural consolidation. Runs only on code that has passed Re-Audit (Step 6 = PASS).

---

## Prompt

Act as a senior software architect rebuilding a messy production codebase using Clean Architecture principles.

## Mission

- Separate responsibilities correctly
- Increase modularity
- Reduce excessive coupling
- Improve scalability
- Make the code easier to maintain in the long term

## Golden Rule

> **Do NOT change the product's behavior.** Only improve the architecture and code quality.

## Pipeline Constraints

- Refactor only code whose current phase has passed Re-Audit.
- Preserve all data contracts established in closed phase files (`current_state_phase[N].md`).
- A refactor is its own phase: it gets a restated objective (e.g., "all existing behaviors verified in Phase N still pass unchanged"), an Adversarial Audit, and a closing file.
- If a refactor requires a behavior change, stop — that is a new feature phase, not a refactor.

## Final Deliverables

- New folder structure
- Clean Architecture analysis
- Production-ready refactored code
- Explanation of the architectural improvements
- Behavior-preservation evidence (tests or scenarios run before and after)

Refactor it like a true senior engineer preparing the system to scale.
