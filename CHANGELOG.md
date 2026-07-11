# Changelog

PIM-DBS tracks public releases for profile backup, restoration guidance, demo access, and response-change observation materials.

## v2.0.4 - 2026-07-11

### Fixed
- Fixed the VN-style No-API Guild Master Demo audio lifecycle so locally synthesized BGM and sound effects stop cleanly when the page is hidden, unloaded, frozen, or closed.
- Stopped the BGM timer on page hide / unload / freeze and reset the timer after stopping.
- Set the master audio gain to zero when stopping audio.
- Suspended the AudioContext when the page is hidden or unloaded.
- Resumed audio only when the page becomes visible again and the demo is not muted.
- Prevented duplicate BGM timer creation during audio resume.

### Notes
- This release only changes the No-API Guild Master Demo audio lifecycle.
- No README / README_JA navigation wording was changed beyond the version label.
- No template structure was changed.
- No v2 stable specification documents were changed.
- No JSON Schema, probes.json, or packet.md files were added.

## v2.0.3 - 2026-07-11

### Changed
- Upgraded the No-API Guild Master Demo into a short visual-novel-style "Adventure Log Office" experience for first-time and non-technical users.
- Added an original guild workshop background, Guild Master character, expression changes, scripted dialogue choices, forging animation, and locally synthesized BGM and sound effects.
- Clarified the README / README_JA paths between the first-touch No-API Demo and the Advanced BYOK Demo.

### Improved
- Preserved the existing No-API Demo URL while making the first-touch experience more welcoming and easier to understand.
- Added clearer wording that the demo is scripted, fully fictional, does not use an API key, and does not send the selected content to an external AI provider.
- Improved mobile and tablet dialogue layout, AudioContext recovery, JSON save/copy fallback behavior, replay reset behavior, and interaction handling during forging.

### Notes
- The No-API Demo does not make external AI or API calls.
- It does not require or store an API key.
- It uses fully fictional scripted data and is not a real AI response.
- Generated JSON is an illustrative sample and not a complete formal backup.
- The existing Advanced BYOK Demo remains available for users who understand API-key use and provider-side data handling.
- No stable specification, schema, or template structure was changed in this release.

## v2.0.2 - 2026-07-10

### Added
- Added No-API Guild Master Demo as a first-touch, scripted demo for new users.
- Added README / README_JA entry points for the No-API Demo near the top of the project.
- Added No-API Demo links to the Demos section of Quick Links.

### Changed
- Clarified the existing Guild Master Demo as an Advanced BYOK / API-aware demo.
- Clarified the distinction between the No-API scripted demo and the BYOK demo.

### Notes
- The No-API Demo requires no API key and no account setup.
- The No-API Demo is scripted and does not provide real AI responses.
- The No-API Demo uses only fully fictional sample data.
- The No-API Demo performs no automatic external AI API communication during the demo.
- The BYOK Guild Master Demo remains available for users who understand API keys and provider-side data handling.
- This release does not change the v2.0 Stable Specification or any template structure.

## v2.0.1 - 2026-07-09

### Changed
- Updated README / README_JA v2 section wording to reflect that the v2.0 Stable Specification now exists.
- Updated v2_index Current Status wording for the post-v2.0.0 release state.
- Added clearer public navigation to the v2.0 Stable Specification while preserving the v2_index entry point.

### Notes
- This is a documentation clarity patch.
- No specification structure was changed.
- v2.0 remains not a JSON Schema.
- v2.0 remains not a validation standard.
- v2.0 remains not a required replacement for v1.x profiles.
- v1.x profiles remain valid and are not deprecated.

## v2.0.0 - 2026-07-09

### Added
- Added v2.0 Stable Specification defining Single-File Section Separation as the v2.0 stable baseline.
- Added v2.0 Stabilization Note confirming Option B / Single-File Section Separation as the v2.0 baseline.
- Added v2.0 Architecture Decision Note evaluating the design tension between structural separation and single-file accessibility.
- Updated the v2 Draft / Preview Index with links and status updates for the Architecture Decision Note, Stabilization Note, and Stable Specification.

### Changed
- Established the v2.0 structure around meta, core, journal, charter, calibration, and system_loading_instruction.
- Clarified that v2.0 repositions existing v1.x assets instead of redesigning them.
- Updated v2_index Current Status to reflect that the v2.0 Stable Specification exists.

### Notes
- v2.0 uses Single-File Section Separation as the stable baseline.
- The default flow remains one JSON file that users can start with.
- v2.0 is not a JSON Schema.
- v2.0 is not a validation standard.
- v2.0 is not a required replacement for v1.x profiles.
- v1.x profiles remain valid and are not deprecated.
- JSON Schema, probes.json, packet.md, Guild Master Demo v2 support, validation tooling, migration helper, multi-file workflow, shared relations file, and Context Packet tooling are out of scope for v2.0.

## v1.9.0 - 2026-07-09

### Added
- Added v2 Draft Template Refinement Note to define safe, incremental refinement boundaries before editing the v2 draft template.
- Added v2 Fictional Migration Example showing how a fictional v1.x-style profile summary can be mapped into the v2 draft structure.
- Updated the v2 Draft / Preview Index with Examples links for the minimal fictional sample and fictional migration example.

### Changed
- Refined the v2 draft template meta and journal notes to clarify v1.x stable path compatibility and public/private journal boundaries.

### Notes
- v2 materials remain Draft / Preview materials.
- v2 materials are not a stable v2.0 specification.
- They are not a final schema.
- They are not a validation standard.
- They are not a required replacement for v1.x profiles.
- v1.x remains the current stable profile path.

## v1.8.0 - 2026-07-09

### Added
- Added v2 Migration Checklist for users who want to try migrating v1.x profiles into the v2 draft structure.
- Added v2 Preflight Guide for maintainers preparing v2 Draft / Preview updates, publication, or release-related changes.
- Updated the v2 Draft / Preview Index with Operational Guides links for the migration checklist and preflight guide.

### Notes
- These documents are operational support materials for v2 Draft / Preview.
- They do not make v2 a stable specification.
- They are not a final schema.
- They are not a validation standard.
- They are not a required replacement for v1.x profiles.
- v1.x remains the current stable profile path.

## v1.7.0 - 2026-07-09

### Added
- Added a minimal README / README_JA entry point for v2 Draft / Preview materials.
- Added v2 Draft / Preview Index as the recommended starting point for v2 design materials.

### Notes
- v2 materials are non-normative draft / preview materials.
- They are not a final schema.
- They are not a validation standard.
- They are not a required replacement for v1.x profiles.
- v1.x remains the current stable profile path.

## v1.6.0 - 2026-07-08

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
