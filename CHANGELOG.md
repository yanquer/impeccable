# Changelog

All notable changes to this project will be documented in this file.

## [Unreleased]

### Added
- Added optional `description-zh` support in `source/skills/*/SKILL.md` for Chinese skill descriptions.
- Added Chinese descriptions for all 21 source skills to improve Codex-side skill discovery.
- Added tests covering `description-zh` parsing, Codex description resolution, and non-Codex fallback behavior.

### Changed
- Updated the Codex transformer so generated Codex skill descriptions use a Chinese-first bilingual format when `description-zh` is present.
- Synced `.codex/skills/*/SKILL.md` with the regenerated Chinese-enabled Codex output.
- Updated contributor documentation to explain `description-zh` and the Codex-specific description mapping behavior.
