# OpenClaw AI Development & Clinical Engineering Team

This workspace houses a multi-agent AI engineering team specialized in Full-Stack Web (React/TypeScript), Backend Systems (Go + Python), and Clinical/Medical Imaging Domain Engineering.

---

## Team Roster

### 📋 Project Management & Orchestration
* **`pm_bot` (Paula)** — Team orchestrator, work decomposition, dependency tracking, and release coordinator.

---

### 🔬 Domain Experts (`domain_experts/`)
* **`domain_experts/research_bot`** — Scientific evidence reviewer, literature validation, and evidence dossier author (`docs/clinical-evidence.md`).
* **`domain_experts/ortho_bot`** — Orthodontic clinical expert, anatomical landmark definitions, measurement protocols, clinical summaries, and threshold policies.
* **`domain_experts/vision_bot`** — Computer vision and medical imaging AI specialist (landmark detection architectures, image quality & distortion checks, Phase 2+).

---

### 💻 Engineering & Interface Design
* **`ux_bot`** — Clinical interface designer, 30–60 second workflow ergonomics, radiograph viewers, and visual overlays.
* **`dev_bot`** — Lead full-stack developer (React 19 + TypeScript, Canvas/SVG overlays, Zustand stores, and Golang backend services).
* **`py_bot`** — Lead Python developer (FastAPI, Docker, automation, and backend services).

---

### 🛡️ Quality Assurance & Operations
* **`qa_bot`** — Quality gatekeeper & test suite architect (author of unit/integration test suites and independent multi-dimensional verification gate).
* **`git_bot`** — GitHub operations, branch management, CI/CD pipeline monitoring, and clean Conventional Commits (sole agent authorized to commit/push).

---

## Standard Workflow

```
User Request → pm_bot
  ├── Stage 1: research_bot (scientific literature review)
  ├── Stage 2: ortho_bot (clinical protocol & landmark definitions)
  ├── Stage 3: ux_bot (interface layout & overlay design)
  ├── Stage 4: dev_bot / py_bot (implementation with domain isolation)
  ├── Stage 5: qa_bot (test suite creation & independent QA verification)
  └── Stage 6: git_bot (git commit, PR, and release upon QA approval)
```

For full details, see [`shared/WORKFLOW.md`](shared/WORKFLOW.md) and individual agent directories.
