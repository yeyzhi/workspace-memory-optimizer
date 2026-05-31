---
name: workspace-memory-optimizer
description: Transform an existing messy folder, project directory, or personal work archive into a reusable Codex memory workspace. Use when the user asks to organize a workspace, create AGENTS.md rules, build a memory/index.md knowledge system, migrate scattered files into projects/docs/outputs/tools, preserve task/project context for future agents, or package a generalized folder-structure method that adapts to the current folder contents rather than a single domain.
---

# Workspace Memory Optimizer

## Purpose

Turn a folder full of mixed source files, outputs, notes, tools, and one-off artifacts into a durable workspace where Codex can recover reusable knowledge before starting future tasks.

Optimize for reusable knowledge first, historical file lookup second. Do not build a diary of every task unless the user explicitly asks.

## Core Workflow

1. **Inventory before changing files**
   - Inspect top-level files/directories, obvious manifests, existing `README.md`/`AGENTS.md`, hidden dependency folders, and large output/source folders.
   - Use `rg --files`, `find -maxdepth`, `du -sh`, and `git status --short` where available.
   - Identify likely categories: projects, source materials, final outputs, reusable docs, tools/scripts, local dependencies/caches, archives.

2. **Infer the workspace domain**
   - Derive themes from filenames, folders, document names, and output types.
   - Avoid hardcoding a domain. A legal workspace, design archive, research folder, consulting folder, software repo, and sales workspace should all produce different knowledge categories.
   - If several domains coexist, create a neutral knowledge index and project cards rather than forcing one taxonomy.

3. **Default to full restructuring**
   - Default mode is **Full**: migrate files into `projects/`, `docs/`, `outputs/`, `tools/`, `archive/`, create `inbox/`, and keep a migration map.
   - Use **Medium** only if the user explicitly asks for minimal movement, the workspace has a strong existing structure, or permissions prevent safe moves.
   - Use **Light** only if the user asks for a non-mutating plan, an index-only setup, or forbids file moves.
   - If implementation is requested, execute the full restructure unless blocked by permission, ambiguity, or destructive risk.
   - Request user approval when an operation needs elevated permissions, moves files outside the target workspace, deletes files, overwrites existing files, or has unclear ownership.
   - Prefer moving noisy dependencies/caches to ignored local storage or adding ignore rules; do not delete them unless the user explicitly approves.

4. **Create the memory-first structure**
   - Default target:
     ```text
     workspace/
     ├── AGENTS.md
     ├── inbox/
     ├── memory/
     │   ├── index.md
     │   ├── proposal-patterns.md
     │   ├── project-lessons.md
     │   ├── customer-faq.md
     │   ├── competitor-research.md
     │   └── mistakes.md
     ├── projects/
     ├── docs/
     └── outputs/
     ```
   - Adapt file names when the workspace is not business/proposal oriented:
     - Research: `research-patterns.md`, `literature-notes.md`, `methods.md`
     - Design/content: `style-patterns.md`, `asset-lessons.md`, `publishing-checks.md`
     - Software: `engineering-patterns.md`, `architecture-decisions.md`, `runbooks.md`
     - Operations: `process-patterns.md`, `stakeholder-faq.md`, `incident-lessons.md`

5. **Write AGENTS.md as the behavioral contract**
   - Require Codex to read `memory/index.md` before any task.
   - Require Codex to select and read the relevant knowledge files before searching project history.
   - Require Codex to check `inbox/` for task-related new files after the knowledge lookup.
   - Require Codex to move matching inbox files into existing projects, or create a new project when no match exists.
   - Require future updates only for reusable knowledge: workflows, decision logic, reusable explanations, customer/stakeholder insights, competitive/market findings, mistakes, and project lessons.
   - Explicitly exclude low-value memory: temporary chat fragments, one-off commands, transient scheduling, caches, dependencies, and build artifacts.

6. **Write memory/index.md as the knowledge router**
   - It should not hold all knowledge.
   - It maps task types and keywords to the files Codex should read first.
   - It should include a rule that project history is second-layer lookup.

7. **Seed knowledge files from existing contents**
   - Extract reusable patterns from filenames and existing artifacts.
   - Keep entries concise and actionable.
   - Prefer “When doing X, first check Y, then decide Z” over “On date A we did B”.
   - Put detailed historical files in project cards, not in the main knowledge files.

8. **Create project cards when useful**
   - For each durable project, create `projects/<date-or-topic>/PROJECT.md`.
   - Include: status, goal, source materials, key outputs, reusable lessons, current gaps, next recommended lookup.
   - Do not force every tiny task into a project.

9. **Create an inbox when the user wants a single drop zone**
   - Add `inbox/README.md`.
   - Tell the user they can place all new files in `inbox/` or `inbox/<task-name>/`.
   - At task start, classify inbox files by filename, folder context, user request, and quick content inspection.
   - If files match an existing project, move them to `projects/<project>/source/`, `work/`, or `outputs/`.
   - If files do not match any existing project, create `projects/YYYY-MM-topic/` with `PROJECT.md`, `source/`, `outputs/`, `notes/`, `work/`, and `archive/`.
   - Keep `inbox/` as a temporary intake area, not long-term storage.

10. **Preserve traceability**
   - For the default full restructure, create `memory/migration-map-YYYY-MM-DD.md`.
   - Record old path -> new path for moved folders/files.
   - Move dependencies/caches to ignored local areas or leave them untouched and add `.gitignore` rules.

11. **Validate**
    - Verify `AGENTS.md` points to `memory/index.md`.
    - Verify `AGENTS.md` tells Codex to check `inbox/` when new files may be present.
    - Verify `memory/index.md` can route representative future tasks.
    - Verify every durable project has a `PROJECT.md`.
    - Verify moved paths are captured in the migration map.
    - Verify `.venv`, `node_modules`, caches, build outputs, `.DS_Store`, and similar noise are ignored.

## Decision Heuristics

- Prefer knowledge categories over task history when future reuse matters.
- Prefer project cards over dumping long histories into `memory/index.md`.
- Prefer full restructuring by default: create durable top-level structure and move clear files into their long-term homes.
- Prefer stable names such as `docs/`, `outputs/`, `tools/`, and `archive/` over deeply customized top-level directories.
- Keep `memory/index.md` short enough to read every time.
- If the folder already has a strong structure, augment it instead of replacing it.
- If files are sensitive or hard to classify, leave them in place and index them rather than moving them.
- Never delete or overwrite user files as part of “cleanup” without explicit approval.

## Useful Deliverables

Depending on the user request, produce one or more:

- A proposed structure plan.
- Implemented directory migration.
- `AGENTS.md`.
- `inbox/README.md`.
- `memory/index.md`.
- Topic knowledge files under `memory/`.
- `projects/*/PROJECT.md` cards.
- `memory/migration-map-YYYY-MM-DD.md`.
- A packaged skill, template, or README for others to reuse.

## Reference Template

For reusable starter text and neutral examples, read `references/structure-template.md`.
