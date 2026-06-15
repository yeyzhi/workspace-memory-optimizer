# Changelog

## 2.0.0 - 2026-06-15

### Changed

- Replaced the older multi-root workspace layout with four visible entrances: `inbox/`, `memory/`, `projects/`, and `library/`.
- Moved reusable templates, tools, and skills under `library/`.
- Changed project scaffolding to create `source/`, `work/`, and `outputs/` only when they contain files.
- Kept project status, notes, decisions, and next lookup in `PROJECT.md` instead of empty placeholder directories.
- Added explicit legacy-layout detection, approval boundaries, and stronger path validation.

### Added

- Added `references/v2-migration.md` for upgrading version 1 workspaces.
- Added version metadata and upgrade guidance to `SKILL.md`.
- Added repository README and release history.

### Migration Notes

This is a breaking structure update. Existing root `docs/`, `outputs/`, `tools/`, `tasks/`, and `archive/` content should be classified by ownership and reuse before being moved. See `references/v2-migration.md`.

## 1.1.0 - 2026-05-31

- Made full restructuring the default behavior.
- Added migration maps, inbox routing, project cards, and memory-first lookup guidance.

## 1.0.0 - 2026-05-31

- Initial public skill release.
