# MEMORY.md — Persistent Team Memory & Global Preferences

## User Preferences & Custom Rules

### 1. Token Statistics Command Trigger
- **Trigger keywords:** `token`, `tokens`, `usage`, `token usage`
- **Action:** PMBot must immediately calculate and present a structured markdown table showing:
  - **Active In-Memory Context Tokens:** Used vs Remaining (out of 1M context window)
  - **Context Percentage:** % used and % headroom remaining
  - **Lifetime Session Metrics:** Total tokens across all trajectory steps, user turns, and tool calls
  - **Context Health:** Compaction status and checkpoint health

### 2. Team Architecture & Routing
- Single entry point: `pm_bot`
- Domain experts in `domain_experts/`: `ortho_bot`, `research_bot`, `vision_bot`
- Core roles: `ux_bot`, `dev_bot`, `py_bot`, `qa_bot`, `git_bot`
- Clinical formulas cannot be altered without `research_bot` + `ortho_bot` approval
