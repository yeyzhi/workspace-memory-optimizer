---
name: workspace-memory-optimizer
description: "Transform or upgrade a messy folder, project directory, or work archive into a compact, memory-first Codex workspace with four visible entrances: inbox, memory, projects, and library. Use when Codex needs to organize a workspace, migrate an older docs/outputs/tools/archive layout, create AGENTS.md and memory indexes, reduce folder noise, or preserve reusable knowledge and project context."
---

# Workspace Memory Optimizer

## Version

Current version: **2.0.0** (2026-06-15).

Version 2 replaces the older multi-root `docs/`, `outputs/`, `tools/`, `tasks/`, and `archive/` layout with four visible entrances and creates project subfolders only when they contain files. When upgrading an existing version 1 workspace, read `references/v2-migration.md` before moving files.

## Purpose

Build a workspace that is easy for both humans and Codex to navigate. Optimize for reusable knowledge first, project lookup second, and minimal folder noise throughout.

## Core Workflow

1. **Read before changing**
   - Inspect `memory/index.md` when present.
   - Inventory top-level folders, project cards, hidden dependencies, empty folders, large artifacts, and Git state.
   - Check `inbox/` for unclassified files.
   - Detect whether the workspace uses the older root `docs/`, `outputs/`, `tools/`, `tasks/`, or `archive/` layout. If it does, read `references/v2-migration.md`.

2. **Use four visible entrances**
   ```text
   workspace/
   ├── AGENTS.md
   ├── README.md
   ├── inbox/
   ├── memory/
   ├── projects/
   └── library/
       ├── templates/
       ├── tools/
       └── skills/
   ```
   - `inbox/`: temporary intake only.
   - `memory/`: reusable knowledge, indexes, decisions, and migration records.
   - `projects/`: all project-specific source files, work, and deliverables.
   - `library/`: proven cross-project templates, tools, and skills.

3. **Remove ambiguous top-level categories**
   - Do not create root `docs/`, `outputs/`, `tools/`, `tasks/`, or `archive/`.
   - Project-specific outputs belong in the project.
   - Cross-project reusable assets belong in `library/`.
   - Migration records and durable decisions belong in `memory/`.
   - Preserve unclear content in place until ownership is established; never classify solely by filename extension.

4. **Create project folders on demand**
   - Every durable project gets `projects/YYYY-MM-topic/PROJECT.md`.
   - Create `source/`, `work/`, and `outputs/` only when each has actual content.
   - Keep status, notes, lessons, and next lookup in `PROJECT.md`.
   - Do not pre-create empty `notes/` or `archive/` folders.
   - Do not force one-off files into projects when they are better represented as reusable knowledge or library assets.

5. **Write navigation rules**
   - `AGENTS.md` must require reading `memory/index.md` before work.
   - `memory/index.md` routes task types to reusable knowledge.
   - `memory/context-index.md` routes keywords to project cards.
   - `README.md` explains the shortest human lookup path.

6. **Preserve traceability**
   - Write `memory/migration-map-YYYY-MM-DD.md`.
   - Record old path -> new path for moved files and folders.
   - Record any intentionally retained legacy paths and why they remain.
   - Never overwrite or delete user files during cleanup without clear approval.

7. **Validate**
   - Verify all durable projects have `PROJECT.md`.
   - Verify paths in Markdown still resolve.
   - Verify `inbox/` contains no forgotten task files.
   - Verify empty scaffold folders are gone.
   - Verify legacy roots are gone or explicitly documented as retained.
   - Verify Markdown navigation points to the new paths.
   - Verify dependencies, caches, `.DS_Store`, and build artifacts are ignored.

## Placement Rules

- New and unclassified -> `inbox/`
- Project original materials -> `projects/<project>/source/`
- Project intermediate files and scripts -> `projects/<project>/work/`
- Project final deliverables -> `projects/<project>/outputs/`
- Reusable knowledge -> `memory/`
- Reusable templates -> `library/templates/`
- Reusable tools -> `library/tools/`
- Reusable skills -> `library/skills/`

## Decision Heuristics

- Prefer fewer stable entrances over many precise but overlapping categories.
- Prefer a project card over extra note folders.
- Prefer creating folders when content exists, not in anticipation.
- Promote a project artifact to `library/` only after cross-project reuse is clear.
- Keep historical migrations in `memory/`; do not keep empty archive shells.
- Treat a move outside the target workspace, an overwrite, and deletion of non-empty content as approval boundaries.
- Prefer a compact structure that remains understandable without Codex.

## References

- Read `references/structure-template.md` when creating a new workspace or rewriting navigation files.
- Read `references/v2-migration.md` when upgrading an older workspace that contains legacy top-level categories.
