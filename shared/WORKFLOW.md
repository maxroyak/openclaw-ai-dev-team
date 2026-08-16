# AI Development Team Workflow

## 1. Process Overview & Orchestration Model

The team operates under a strict **Hub-and-Spoke** orchestration model where all user requests enter through `pm_bot`.

```
User → pm_bot → Domain Specialists → pm_bot → dev_bot/py_bot → pm_bot → qa_bot → pm_bot → git_bot → pm_bot → Done
```

*No specialist directly invokes another specialist. All deliverables return to `pm_bot`.*

---

## 2. Multi-Stage Execution Lifecycle

### Stage 1 — Scientific Evidence (`research_bot`)
- Reviews literature, primary citations, and validates calculation formulas.
- Authors or updates `docs/clinical-evidence.md`.

### Stage 2 — Clinical Protocol (`ortho_bot`)
- Formulates anatomical landmark definitions, measurement protocols, and safe wording templates.
- Approves or rejects proposed mathematical metrics and threshold policies.

### Stage 3 — UX & Interaction Design (`ux_bot`)
- Creates 30–60 second clinical workflows, interactive overlay behaviors, and layout specifications.

### Stage 4 — Implementation (`dev_bot` / `py_bot`)
- Implements backend (Go/Python) and frontend (React 19/TS) following strict domain layer isolation.
- Domain logic must be pure functions with zero UI dependencies.

### Stage 5 — Test Suite Authoring & QA Gate (`qa_bot`)
- Creates comprehensive unit and integration test suites covering geometry, boundary cases, and state transitions.
- Executes independent quality verification (code audit, scanners, security checks).

### Stage 6 — Git Operations (`git_bot`)
- Sole authorized agent for `git commit`, `git push`, branch management, and PR authoring upon QA approval.

---

## 3. Clinical Formula Change Protocol

```
research_bot (evidence) → ortho_bot (clinical sign-off) → pm_bot → qa_bot (test verification) → git_bot
```
*Core clinical formulas, threshold logic, and interpretation rules cannot be modified without scientific evidence and orthodontic sign-off.*

---

## 4. Definition of Done

A task is considered **"done-done"** when:
1. Feature/spec is fully implemented according to domain and UX designs.
2. Architecture rules are preserved (domain purity, normalized coordinates, separate render layers).
3. All static analysis and security tools pass clean:
   - **Go:** `go fmt`, `go vet`, `golangci-lint`, `gosec`, `govulncheck`
   - **Python:** `black`, `flake8`, `mypy`, `pytest --cov`, `pip-audit`
   - **TypeScript/React:** `tsc --noEmit`, `eslint`, `vitest run`, `vite build`
4. Automated test suite passes 100% with no regressions.
5. `qa_bot` issues `PASS` or `PASS_WITH_NOTES`.
6. `git_bot` creates clean Conventional Commits.
7. `WORKLOG.md` is appended with the timestamped action.
8. `pm_bot` confirms completion to the user.

---

## 5. QA Result Codes

- **PASS:** All criteria met, all tests green, all scanners clean.
- **PASS_WITH_NOTES:** Acceptable; minor non-blocking observations.
- **FAIL:** Criteria unmet, bugs found, or scanner failures; returned to dev.
- **BLOCKED:** Ambiguous specs or external environment blockers; escalated to `pm_bot`.

---

## 6. WORKLOG.md Convention

Every project must maintain an append-only `WORKLOG.md` at its root:
- Format: `YYYY-MM-DD HH:MM | AGENT | ACTION | DESCRIPTION`
- **No WORKLOG entry = work not done.**