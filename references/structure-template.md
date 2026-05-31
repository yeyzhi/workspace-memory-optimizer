# Structure Template

Use this as a neutral starter. Adapt category names to the folder's actual content.

## AGENTS.md Template

```markdown
# Codex Working Rules

This workspace is memory-first. Before starting any task, read `memory/index.md`, decide whether reusable knowledge exists, then read the relevant knowledge files.

Default restructuring mode is full restructuring: create durable top-level folders, move clear files into their long-term homes, and preserve traceability with a migration map.

## Required Lookup

1. Read `memory/index.md`.
2. Match the user task to the knowledge directory.
3. Read the relevant knowledge files before searching raw project files.
4. Check `inbox/` for task-related new files.
5. If inbox files match an existing project, move them into that project.
6. If inbox files do not match an existing project, create a new `projects/YYYY-MM-topic/` project with a `PROJECT.md`.
7. If project history is needed, read the matching `projects/<project>/PROJECT.md`.
8. Only then inspect source materials, outputs, tools, or archives.

## Update Rule

At the end of a task, update memory only when the work produced reusable knowledge:

- workflows and decision logic
- reusable explanations or templates
- project lessons
- stakeholder/customer insights
- competitor or market findings
- mistakes, risks, and delivery lessons

Do not record temporary chat, one-off commands, transient scheduling, dependency folders, caches, or build artifacts.

## Restructuring Rule

When asked to optimize or organize this workspace, default to full restructuring:

- Move clear project materials into `projects/<project>/`.
- Move reusable docs/templates into `docs/`.
- Move reusable tools/scripts into `tools/`.
- Move cross-project final exports into root `outputs/`.
- Move low-frequency historical material into `archive/`.
- Create or update `memory/migration-map-YYYY-MM-DD.md`.
- Keep caches, dependencies, and build artifacts ignored.

Ask for user approval before moving files outside the workspace, deleting files, overwriting files, or making a move whose ownership is unclear.

## Inbox Rule

Users may place all new files in `inbox/` or `inbox/<task-name>/`.

During each task:

- Classify relevant inbox files by task request, filename, folder context, and quick content inspection.
- Move original materials to `projects/<project>/source/`.
- Move intermediate or to-be-processed files to `projects/<project>/work/`.
- Move final deliverables to `projects/<project>/outputs/`.
- Move reusable knowledge to `memory/`.
- Move reusable templates or documentation to `docs/`.
- Move reusable tools to `tools/`.
- Create a new project if no existing project matches.
```

## memory/index.md Template

```markdown
# Memory Index

This is the workspace knowledge router. Read this file before starting any task.

## Knowledge Directory

| Task type | Keywords | Read first | Then read |
| --- | --- | --- | --- |
| Plans / proposals | proposal, plan, pitch, solution, PRD, requirements | `memory/proposal-patterns.md` | `memory/project-lessons.md`, `memory/mistakes.md` |
| Project lessons | retrospective, similar project, lessons, case study | `memory/project-lessons.md` | `projects/<project>/PROJECT.md` |
| Stakeholder FAQ | customer, stakeholder, FAQ, objection, answer | `memory/customer-faq.md` | `memory/project-lessons.md` |
| Research / competitors | competitor, market, benchmark, procurement, research | `memory/competitor-research.md` | `memory/context-index.md` |
| Mistake avoidance | risk, pitfall, mistake, avoid, review | `memory/mistakes.md` | `memory/project-lessons.md` |
| Historical files | source file, old output, previous version, where is | `memory/context-index.md` | `projects/<project>/PROJECT.md` |
| New file intake | inbox, new files, classify, organize, import, create project | `inbox/README.md` | `memory/context-index.md`, `projects/<project>/PROJECT.md` |

## Quality Rules

- Store reusable knowledge, not task logs.
- Write future-useful rules and patterns.
- Keep detailed historical material in project cards.
```

## PROJECT.md Template

```markdown
# Project Name

## Status

Current state in one or two sentences.

## Goal

What this project is for.

## Source Materials

- `source/`

## Key Outputs

- `outputs/`

## Reusable Lessons

- Future-useful patterns or decisions from this project.

## Current Gaps

- Unknowns or cleanup needed.

## Next Lookup

What a future agent should read first.

## Last Updated

YYYY-MM-DD
```

## Generic Top-Level Structure

```text
workspace/
├── AGENTS.md
├── README.md
├── inbox/
│   └── README.md
├── memory/
│   ├── index.md
│   ├── proposal-patterns.md
│   ├── project-lessons.md
│   ├── customer-faq.md
│   ├── competitor-research.md
│   ├── mistakes.md
│   └── migration-map-YYYY-MM-DD.md
├── projects/
│   └── <project>/
│       ├── PROJECT.md
│       ├── source/
│       ├── outputs/
│       ├── notes/
│       ├── work/
│       └── archive/
├── docs/
├── outputs/
├── tools/
└── archive/
```

## inbox/README.md Template

```markdown
# Inbox

Place new files here when you do not know where they belong.

Codex should check this folder during each task, then move relevant files to an existing project or create a new project.

## Routing Rules

- Original materials -> `projects/<project>/source/`
- In-progress or to-be-processed files -> `projects/<project>/work/`
- Final outputs -> `projects/<project>/outputs/`
- Reusable knowledge -> `memory/`
- Reusable docs/templates -> `docs/`
- Reusable tools/scripts -> `tools/`

If no project matches, create `projects/YYYY-MM-topic/` with `PROJECT.md`, `source/`, `outputs/`, `notes/`, `work/`, and `archive/`.
```

## Adaptation Examples

- Consulting/sales: `proposal-patterns.md`, `customer-faq.md`, `competitor-research.md`.
- Research: `research-patterns.md`, `methods.md`, `literature-notes.md`, `mistakes.md`.
- Design/content: `style-patterns.md`, `asset-lessons.md`, `publishing-checks.md`.
- Software: `engineering-patterns.md`, `architecture-decisions.md`, `runbooks.md`, `postmortems.md`.
- Personal knowledge: `life-admin-patterns.md`, `finance-notes.md`, `decision-log.md`.
