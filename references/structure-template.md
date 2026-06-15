# Compact Structure Template

Use this reference when creating a new version 2 workspace or rewriting its navigation files.

## Target

```text
workspace/
├── AGENTS.md
├── README.md
├── inbox/
│   └── README.md
├── memory/
│   ├── index.md
│   ├── context-index.md
│   ├── decisions.md
│   └── migration-map-YYYY-MM-DD.md
├── projects/
│   └── YYYY-MM-topic/
│       ├── PROJECT.md
│       ├── source/   # create only when needed
│       ├── work/     # create only when needed
│       └── outputs/  # create only when needed
└── library/
    ├── README.md
    ├── templates/
    ├── tools/
    └── skills/
```

## Routing

| Content | Destination |
| --- | --- |
| Unclassified new file | `inbox/` |
| Project source | `projects/<project>/source/` |
| Project intermediate work | `projects/<project>/work/` |
| Project final deliverable | `projects/<project>/outputs/` |
| Reusable knowledge or decision | `memory/` |
| Reusable template | `library/templates/` |
| Reusable tool | `library/tools/` |
| Reusable skill | `library/skills/` |

## Rules

- Do not create root `docs/`, `outputs/`, `tools/`, `tasks/`, or `archive/`.
- Do not pre-create empty project subdirectories.
- Put project notes and status in `PROJECT.md`.
- Create a migration map whenever paths move.
- Keep `memory/` flat until a topic has enough real files to justify a subdirectory.
- Keep dependencies and caches in ignored hidden directories such as `.local/`.

## Minimum AGENTS.md Contract

Require future agents to:

1. Read `memory/index.md` before starting work.
2. Read topic knowledge before searching project history.
3. Check `inbox/` for task-related files.
4. Use `memory/context-index.md` and `PROJECT.md` to locate historical material.
5. Route project-specific files to the project and reusable assets to `library/`.
6. Create project subdirectories only when they contain files.
7. Update memory only when the task produces reusable knowledge.

## Minimum PROJECT.md Contract

Each durable project card should state:

- status and goal
- actual source material paths, when present
- actual work and output paths, when present
- important decisions and reusable lessons
- current gaps and the next recommended lookup
- last updated date

Do not list empty placeholder paths.
