# Workspace Memory Optimizer

A Codex skill for turning a messy folder or older memory workspace into a compact, reusable, memory-first workspace.

## Current Version

**v2.0.0 - 2026-06-15**

Version 2 introduces a four-entrance structure:

```text
workspace/
├── inbox/     # temporary intake
├── memory/    # reusable knowledge and navigation
├── projects/  # project-specific source, work, and outputs
└── library/   # reusable templates, tools, and skills
```

Project subfolders are created only when they contain files. The older root `docs/`, `outputs/`, `tools/`, `tasks/`, and `archive/` categories are migrated according to ownership and reuse.

## Install

Copy or install this repository as `workspace-memory-optimizer` under your Codex skills directory, then invoke `$workspace-memory-optimizer` when organizing or upgrading a workspace.

## Files

- `SKILL.md`: core workflow and current version
- `references/structure-template.md`: compact version 2 target structure
- `references/v2-migration.md`: migration guidance for version 1 workspaces
- `agents/openai.yaml`: Codex UI metadata
- `CHANGELOG.md`: release history

## Safety

The skill preserves traceability with migration maps and treats deletion, overwrites, unclear ownership, and moves outside the target workspace as approval boundaries.
