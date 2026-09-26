# Deterministic Context Protocol (DCP) 🚀

> **Phase-Driven Agentic Engineering System for Claude Code, Cursor, Windsurf & LLM CLI tools.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Architecture: File-Based](https://img.shields.io/badge/Architecture-File--Based%20State-blue)](#)
[![RAG Alternative: Zero-Cost](https://img.shields.io/badge/RAG%20Alternative-Zero--Cost-green)](#)

DCP is a deterministic, file-based context management and multi-agent orchestration framework designed to eliminate context loss, hallucinations, and superficial fixes when building complex software with AI agents.

Instead of relying on probabilistic vector databases (RAG) or unbounded chat histories, **DCP turns project execution into a strict finite state machine driven by Markdown artifacts.**

---

## 💡 Why DCP over vector DBs / memory plugins?

| Problem in agentic coding | Traditional solution (vector DBs / RAG) | DCP Framework solution |
| :--- | :--- | :--- |
| **Context loss** | Probabilistic similarity search — may miss critical details | **Deterministic chronological state reconstruction** |
| **Superficial fixes** | Trial-and-error patching directly on files | **Adversarial audit → root cause analysis → minimal safe fix** |
| **Architecture drift** | The agent writes code without consulting previous decisions | **Mandatory restated objective before any implementation** |
| **Cost & latency** | Cloud infrastructure, API keys, network overhead | **Free, Git-native, local Markdown files** |

---

## ⚙️ The 5-layer execution pipeline

DCP enforces a strict assembly line for AI agents:

```
┌────────────────────────┐
│ 01. Context Memory     │ ──> Reconstructs full project state from closed phase files
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│ 02. CTO Orchestrator   │ ──> Activates specialists & defines an observable strategy
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│ 03. Adversarial Audit  │ ──> Paranoid bug discovery (🔴 Blocker / 🟡 Major / 🟢 OK)
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│ 04. Debugging Machine  │ ──> Traces root cause & designs the minimal safe fix
└───────────┬────────────┘
            ▼
┌────────────────────────┐
│ 05. Clean Refactoring  │ ──> Clean Architecture consolidation, zero behavior change
└────────────────────────┘
```

The pipeline is not linear-only: Step 6 (Re-Audit) sends failures back to Step 5, and a strategy failure back to Step 2. Nothing advances until a phase closes.

---

## 🛠️ Quick start

### 1. Installation

Copy the `skills/` folder into your agent's rules path:

| Tool | Path |
| :--- | :--- |
| Claude Code | `.claude/skills/` or project `CLAUDE.md` |
| Cursor | `.cursor/rules/` |
| Windsurf | `.windsurf/rules/` |
| Generic LLM CLI | system prompt / prompt library |

### 2. File setup

Keep closed phase files at a fixed, established path in your project:

```text
/your-project
├── current_state_phase1.md
├── current_state_phase2.md
└── estado_actual.md          # cumulative state — the encoded sum of the phases
```

### 3. Execution rule

Start any session with:

> *"Execute this session using the DCP Framework. Load skill `01-context-memory`, reconstruct the state, and proceed with Phase N."*

The agent must not write code until the state is reconstructed and the objective is restated observably.

---

## 📁 Skill registry

| Skill | Purpose |
| :--- | :--- |
| [`01-context-memory.md`](skills/01-context-memory.md) | Enforces strict chronological reading of closed phase files (`current_state_phase[N].md`) before any action. Phase files outrank the cumulative summary. |
| [`02-orchestrator.md`](skills/02-orchestrator.md) | Coordinates Architect, Reviewer, Database, DevOps, Security, and Onboarding roles under an evidence-first principle. Contains the 8-step Phased Build Protocol. |
| [`03-adversarial-audit.md`](skills/03-adversarial-audit.md) | Evaluates code under extreme boundary conditions (nulls, zero-division, empty data, scope shifts) and forbids "no bugs found" without ≥5 tested scenarios. |
| [`04-debugging-machine.md`](skills/04-debugging-machine.md) | Isolates true root causes from secondary symptoms and produces the minimal safe fix with regression checks. |
| [`05-clean-refactoring.md`](skills/05-clean-refactoring.md) | Refactors audited code into Clean Architecture without altering product behavior. |

## 📄 The phase closing file

Every phase ends with a `current_state_phase[N].md` written to the established path. It records the restated objective and its verification, deliverables, files changed, strategy applied, audit findings and fixes, known limitations, rollback instructions, and the next phase's entry conditions.

A worked reference: [`examples/current_state_phase1.md`](examples/current_state_phase1.md).

---

## 🔒 Hard rules

- No code in Steps 1 (Analyze) or 2 (Strategy).
- No advancement while Re-Audit = FAIL.
- No files saved outside the user's established path.
- No invented bugs in the audit or re-audit.
- No fix that introduces new bugs — report it as an unresolvable conflict instead.
- One phase = one cycle. Never mix phases.

---

## 🤝 Contributing & license

Contributions are welcome — open an issue or a PR to improve the activation matrix or the audit checklists.

Licensed under the [MIT License](LICENSE).

---

### Suggested repository topics

`claude-code` · `agentic-ai` · `cursor-rules` · `context-management` · `software-architecture` · `prompt-engineering`
