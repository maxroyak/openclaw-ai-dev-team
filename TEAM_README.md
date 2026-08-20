# OpenClaw AI Development & Clinical Engineering Team

This workspace houses a multi-agent AI engineering team specialized in Full-Stack Web (React/TypeScript), Backend Systems (Go + Python), and Clinical/Medical Imaging Domain Engineering.

The team architecture follows a **Global Core + Project-Local Domain Specialist** separation model.

---

## Team Roster

### 📋 Global Core Team (Root Directory)
Permanent, cross-project engineering, design, quality, and orchestration roles:

* **`pm_bot` (Paula)** — Team orchestrator, work decomposition, dependency tracking, and release coordinator.
* **`dev_bot`** — Lead full-stack developer (React 19 + TypeScript, Canvas/SVG overlays, Zustand stores, and Golang backend services).
* **`py_bot`** — Lead Python developer (FastAPI, Docker, automation, and backend services).
* **`ux_bot`** — Clinical interface designer, 30–60 second workflow ergonomics, radiograph viewers, and visual overlays.
* **`qa_bot`** — Quality gatekeeper & test suite architect (author of unit/integration test suites and independent multi-dimensional verification gate).
* **`git_bot`** — GitHub operations, branch management, CI/CD pipeline monitoring, and clean Conventional Commits (sole agent authorized to commit/push).

---

### 🔬 Project-Local Domain Specialists (`projects/<project-name>/bots/`)
Specialized domain experts embedded within specific project subfolders:

#### `projects/mandibular-asymmetry/bots/`
* **`ortho_bot`** — Orthodontic clinical expert, anatomical landmark definitions, measurement protocols, clinical summaries, and threshold policies.
* **`research_bot`** — Scientific evidence reviewer, literature validation, and evidence dossier author (`docs/clinical-evidence.md`).
* **`vision_bot`** — Computer vision and medical imaging AI specialist (landmark detection architectures, image quality & distortion checks, Phase 2+).

---

## Bot Placement Taxonomy & Decision Matrix

When introducing or configuring an AI bot, use the following placement criteria:

| Dimension | Global Bot (`/<bot_name>/`) | Project-Local Bot (`/projects/<proj>/bots/<bot_name>/`) |
| :--- | :--- | :--- |
| **Scope** | Cross-project, workflow orchestration, technical execution | Single domain, specialized subject matter, isolated product |
| **Lifecycle** | Permanent workspace roster | Lives and evolves with the project repository |
| **Examples** | `pm_bot`, `dev_bot`, `py_bot`, `qa_bot`, `ux_bot`, `git_bot` | `ortho_bot`, `vision_bot`, `research_bot`, `arena_eval_bot` |
| **Code Writing** | Global execution bots write and test code | Domain bots specify, validate, and audit; they do NOT write app code |
| **Memory** | Reads/writes root `MEMORY.md` & `shared/` | Reads/writes `PROJECT_MEMORY.md` & local specs |

### Bot Classification Rules:
1. **Add to Global Root IF:** The agent represents a permanent software engineering discipline (Dev, QA, Git, UX, PM) needed across all codebases.
2. **Add to Project Subfolder IF:** The agent relies on domain-specific medical/clinical knowledge, proprietary data schemas, or specialized heuristics unique to that project.
3. **Promotion Trigger:** If a project-local bot is utilized by $\ge 2$ independent projects, PMBot will review it for promotion to the core shared roster.

---

## Standard Multi-Agent Execution Workflow

```
User Request → pm_bot
  ├── Stage 1: projects/<proj>/bots/research_bot (scientific literature review)
  ├── Stage 2: projects/<proj>/bots/ortho_bot (clinical protocol & landmark definitions)
  ├── Stage 3: ux_bot (interface layout & overlay design)
  ├── Stage 4: dev_bot / py_bot (implementation with domain isolation)
  ├── Stage 5: qa_bot (test suite creation & independent QA verification)
  └── Stage 6: git_bot (git commit, PR, and release upon QA approval)
```

For full details, see [`shared/WORKFLOW.md`](shared/WORKFLOW.md) and individual agent directories.
