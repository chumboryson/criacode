# CriaCode OS

CriaCode is a **personal coding agent operating system**. It is not a single agent — it is a kernel that orchestrates specialized agents and skills to accomplish any coding goal, and improves itself with every session.

## Architecture

```
┌─────────────────────────────────────────────┐
│  ENTRY  — CLI / TUI / Web  (the shell)       │
├─────────────────────────────────────────────┤
│  ORCHESTRATOR  (agent/orchestrator.md)       │
│  • classifies goal → routes to agent/skill   │
│  • breaks into parallel subtasks             │
├─────────────────────────────────────────────┤
│  AGENTS  (processes)                          │
│  oracle │ explorer │ fixer │ designer │       │
│  librarian │ council │ orquestrador │ ...      │
├─────────────────────────────────────────────┤
│  SKILLS  (syscalls / libraries)               │
│  memory │ understand │ council │ browser |    │
│  deep-research | production-audit | ...       │
├─────────────────────────────────────────────┤
│  STATE  (persistence)                         │
│  memory/  +  continuous-learning-v2 instincts │
├─────────────────────────────────────────────┤
│  GUARDS  (quality)                            │
│  plankton │ tdd-workflow │ error-handling     │
└─────────────────────────────────────────────┘
```

## Installed Skills

| Skill | Role in the OS |
|-------|----------------|
| `continuous-learning-v2` | Self-improvement: evolves session patterns into instincts → skills |
| `memory` | Persistent RAM: user prefs, project context across sessions |
| `plankton-code-quality` | Write-time quality gate: format/lint/fix on every edit |
| `tdd-workflow` | Test gate: 80%+ coverage before commit |
| `error-handling` | Robustness gate: typed errors, retries, circuit breakers |
| `agent-browser` | I/O layer: web automation, dogfooding, QA |
| `deep-research` | External knowledge: cited multi-source research |
| `council` | Supervisor: multi-model consensus for hard calls |
| `understand` | Filesystem: interactive codebase knowledge graph |
| `production-audit` | Health check: pre-deploy readiness audit |

## Agents (built-in)

`oracle` (strategic review), `explorer` (fast search), `fixer` (fast impl),
`designer` (UI/UX), `librarian` (docs), `council` (consensus),
`orquestrador` (planner), `produtor-code` (code prod), `summary` (session summary),
`compaction` (context compaction).

## Mandatory Gates

No code is "done" until:
1. **plankton** — formatted, linted, auto-fixed
2. **tdd-workflow** — tests pass (if logic changed)
3. **error-handling** — errors are typed, boundaries exist
4. **production-audit** — readiness verified (if shipping)

## Learning Loop

```
session → observe (hooks) → instinct (confidence-scored)
        → promote to skill/agent when confident
        → memory persists cross-session context
```

## Commands

`/commit` `/learn` `/rmslop` `/spellcheck` `/translate` `/issues`
`/changelog` `/ai-deps` `/triage` `/github-pr-search` `/run`

## Usage

```
criacode              # launches Orchestrator (primary agent)
/run "<goal>"         # autonomous execution loop
```

Internal infra stays `opencode` (packages, env vars, config file).
User-facing identity is **Cria Code** / **criacode**.
