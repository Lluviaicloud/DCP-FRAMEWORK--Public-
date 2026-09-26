# 01 — Context Memory

**Role in the pipeline:** State reconstruction. Runs first in every session or phase.

---

## Description

Before starting any new session or phase, do not assume previous conversation context.
Reconstruct the project state by reading, in this mandatory order:

1. **All individual closed phase files, in chronological order** (`current_state_phase1.md`, `current_state_phase2.md`, `current_state_phase3.md`, ...). Each phase file is primary evidence — read and analyze the conclusions of every phase before moving to step 2. Do not skip any phase file, even if a later summary exists.
2. **The cumulative state file** (`estado_actual.md` / `estado_adversial.md` or equivalent). This file must be understood as the encoded sum of the phase files read in step 1 — not as an independent source. If the cumulative file contradicts or omits something present in an individual phase file, the phase file is authoritative and the discrepancy must be flagged before proceeding.
3. **Any additional phase summaries** required for the current phase scope.
4. **The current project files.**

Only after reconstructing the complete project state — phases first, cumulative state second — may implementation begin.

## Missing evidence

If any individual phase file is missing or inaccessible, **stop and report which phase is missing** before reading the cumulative state file. Reading the cumulative file without its underlying phases is not a valid state reconstruction.

## New project / new context

If no state files exist (`estado_actual.md`, `estado_fase.md`, `estado_adversial.md`, or any `current_state_phase[N].md`), this is a new project or new context, not a missing-evidence error. In this case, the project state is defined by:

1. The user's explicitly stated objective for this session.
2. Any sources/files attached to the current conversation (documents, specs, existing code).

No prior phase may be assumed, inferred, or invented. Proceed to Step 1 (ANALYZE) using only what the user has stated and attached — do not ask the user to "confirm" a phase history that doesn't exist, and do not treat the absence of files as a blocker requiring the user to search their filesystem.

## Source of truth

The latest closed phase is the sum of the phases and the single source of truth.
