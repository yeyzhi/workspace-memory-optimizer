# Version 2 Migration

Read this reference only when upgrading a workspace that uses the older multi-root structure.

## Breaking Changes

| Version 1 location | Version 2 destination |
| --- | --- |
| root `docs/` | `library/templates/`, `memory/`, or a matching project |
| root `outputs/` | matching project `outputs/` or `library/templates/` |
| root `tools/` | `library/tools/` |
| root `tasks/` | active project card or durable decision in `memory/` |
| root `archive/` | matching project or migration record in `memory/` |
| empty project `notes/` and `archive/` | remove after confirming they contain no files |

Classify by ownership and reuse, not by the old folder name:

- Project-specific material stays with its project.
- Proven cross-project assets move to `library/`.
- Reusable knowledge, decisions, indexes, and migration records move to `memory/`.
- Unclear new material moves to `inbox/` or remains in place until classified.

## Migration Workflow

1. Read existing `AGENTS.md`, `README.md`, `memory/index.md`, and project cards.
2. Inventory legacy roots, project folders, empty directories, large files, dependencies, and caches.
3. Create `library/templates/`, `library/tools/`, and `library/skills/` only as needed.
4. Move clear content and record every move in `memory/migration-map-YYYY-MM-DD.md`.
5. Rewrite navigation and storage rules to use the four visible entrances.
6. Remove only confirmed-empty legacy directories.
7. Validate that every project has `PROJECT.md`, all referenced paths resolve, and no task files remain forgotten in `inbox/`.

## Approval Boundaries

Request approval before:

- deleting non-empty files or folders
- moving files outside the target workspace
- overwriting an existing destination
- resolving unclear ownership by guesswork

Do not treat broken Git objects, caches, or sync-conflict copies as business content without verifying them first.
