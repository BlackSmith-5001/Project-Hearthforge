# Changelog

PIM-DBS v1.5 is a guided profile creation demo release. It adds Guild Master Demo materials without introducing CLI Observation Bands, JSON template schema changes, or v2.0 architecture changes.

## v1.6.0 - Unreleased

### Added
- Response Change Bands formal guides in English and Japanese.
- Glossary entries for Response Change Bands / RCB.
- FAQ clarification that RCB is not a measurement of AI internal state.
- Cross-links between Response Change Catalog and Response Change Bands.

### Changed
- README (EN/JA): added Response Change Bands to Guides while keeping the design notes under Reference.
- README (EN/JA): updated the older CLI architecture wording to RCB.
- Glossary (EN/JA): marked CLI / Cognitive Load Index as deprecated historical wording.

### Scope
- Formal RCB migration for user-side response-change observation.
- No JSON template change.
- No JSON Schema, probes, or calibration files.
- No Guild Master Demo changes.
- No v2.0 architecture changes.

## v1.5.2 - 2026-07-08

### Added
- Response Change Bands design notes in English and Japanese.

### Scope
- Design notes only.
- No Glossary migration.
- No README conceptual rewrite.
- No FAQ rewrite.
- No JSON template change.
- No v2.0 architecture changes.

## v1.5.1 - 2026-07-08

### Changed
- README (EN/JA): added the GitHub Pages live demo link for the Guild Master Demo.
- README (EN/JA): kept the local source link and added fallback guidance for downloading and opening the HTML file directly.
- README (EN/JA): clarified that browser-based BYOK API calls may be affected by provider API behavior or CORS policy.
- Guild Master Prompt: softened the note about future Dialogue Exemplars provenance support.

### Scope
- Focused on Guild Master Demo discoverability and safety wording.
- No RCB formal migration, CLI Observation Bands, Glossary changes, JSON template changes, or v2.0 architecture changes are included.

## v1.5.0 - 2026-07-07

### Added
- Guild Master Demo HTML version for guided browser-based profile creation.
- Guild Master Prompt version for chat-based guided profile creation.

### Scope
- Focused on guided profile creation demos.
- No CLI Observation Bands are included.
- No v2.0 architecture changes are included.
- No JSON template schema change is included.

## v1.4.0 - 2026-07-07

### Added
- Response Change Catalog documents in English and Japanese.

### Changed
- README (EN/JA): added Response Change Catalog to the Quick Links.
- FAQ (EN/JA): added a pointer to the Response Change Catalog for unstable or mismatched responses.

### Scope
- Kept v1.4.0 focused on observed response changes and user-side responses.
- CLI Observation Bands and v2.0 architecture changes are not included.

## v1.3.0 - 2026-07-07

### Added
- FAQ documents in English and Japanese.
- Discussion Prompts documents for external review and community questions.

### Changed
- JSON Guide (EN/JA): added a lightweight Temporal Anchor note as an optional user-provided session reference.
- README (EN/JA): added FAQ and Discussion Prompts to the Quick Links.

### Scope
- Kept v1.3 focused on external-readiness documentation and lightweight safety clarification.
- v2.0 architecture changes are not included.

## v1.2.0 - 2026-07-07

### Added
- Public/private instance separation guides in English and Japanese.
- JSON Guide in English and Japanese.
- Self-Forge Guide in English and Japanese.
- A fully fictional example persona in JSON and Markdown formats.
- Restoration Verification Example documents in English and Japanese.

### Changed
- README (EN/JA): added a "Start Here" workflow and grouped the Quick Links for first-time users.

## v1.1.0

- Added Provenance support for Shared Episodes.
- Added Dialogue Exemplars for response-style reconstruction.
- Added Restoration Verification fields for post-reload checks.
- Added Model Notes for model-specific behavior tracking.
- Added `templates/self_forge_prompt.md`.
- Updated README EN/JA and Glossary EN/JA for verification fields and safety clarifications.
- Clarified that JSON is the full v1.1.0 format and Markdown is a beginner-friendly simplified format.

## v1.0.0

- Initial public release of PIM-DBS.
- Introduced user-side persona/context backup and restoration workflow.
- Added README EN/JA, glossary documents, and initial JSON/Markdown templates.
- Established safety framing: prompt-based usage only, no model modification, no safeguard bypass.
