# PIM-DBS v2.0 Index

This is an internal index for the current PIM-DBS v2.0 design materials.

It is not a formal public entry point, not a release note, and not a v2.0 specification. It exists to make the v2.0 concept notes, draft decisions, migration notes, and draft template easier to read in order.

## 1. Purpose

The v2.0 design set has grown into several related files.

This index explains:

- what each file is for
- which order to read them in
- what the current status of v2.0 is
- what is intentionally not included yet
- which safety boundaries remain fixed across the design work

README uses this index as the minimal v2 Draft / Preview entry point. Individual v2 notes are not listed directly in README.

## 2. Current Status

- v2.0 is not a formal specification yet.
- The v2 draft template is a non-normative draft.
- The v1.x canonical template remains valid.
- The v2 draft is not a required replacement for v1.x profiles.
- README uses the v2 index as a minimal v2 Draft / Preview entry point.
- The v2 materials are design and review artifacts unless otherwise noted.

## 3. Recommended Reading Order

1. [Concept Study](v2_concept_study_en.md)
2. [Field Mapping Note](v2_field_mapping_note_en.md)
3. [Public Example Design Note](v2_public_example_design_note_en.md)
4. [Minimal Fictional Sample](v2_minimal_sample_fictional_en.md)
5. [Fictional Migration Example](v2_migration_example_fictional_en.md)
6. [Template Shape Note](v2_template_shape_note_en.md)
7. [Draft Template Decisions Note](v2_draft_template_decisions_en.md)
8. [Architecture Decision Note](v2_architecture_decision_note_en.md)
9. [Stabilization Note](v2_stabilization_note_en.md)
10. [Stable Specification](v2_stable_specification_en.md)
11. [v2 Draft Template](../templates/pim-dbs_v2_draft.json)
12. [Migration Guidance Note](v2_migration_guidance_note_en.md)
13. [Migration Checklist](v2_migration_checklist_en.md)
14. [Preflight Guide](v2_preflight_guide_en.md)

This order starts with purpose and scope, then moves through mapping, public example safety, fictional examples, template decisions, architecture direction, stabilization direction, the stable specification, the draft itself, migration guidance, and operational checks.

## 4. File Roles

| File | Role |
| --- | --- |
| [Concept Study](v2_concept_study_en.md) | Explains the purpose, scope, proposed structure, safety boundaries, and open questions for v2.0. |
| [Field Mapping Note](v2_field_mapping_note_en.md) | Maps v1.x fields and concepts into the candidate `core`, `journal`, `charter`, and `calibration` areas. |
| [Public Example Design Note](v2_public_example_design_note_en.md) | Defines what can and cannot be shown in public examples. |
| [Minimal Fictional Sample](v2_minimal_sample_fictional_en.md) | Shows a fully fictional worked example of the candidate v2.0 structure. |
| [Fictional Migration Example](v2_migration_example_fictional_en.md) | Shows a fully fictional migration example from a v1.x-style profile summary into the v2 draft structure. |
| [Template Shape Note](v2_template_shape_note_en.md) | Explores possible template shape, top-level sections, and unresolved structural choices. |
| [Draft Template Decisions Note](v2_draft_template_decisions_en.md) | Records provisional decisions made before creating the first v2 draft template. |
| [Architecture Decision Note](v2_architecture_decision_note_en.md) | Evaluates the tension between structural separation and single-file kindness, including Option B / Single-File Section Separation as a possible v2.0 baseline. It is not the v2.0 stable specification. |
| [Stabilization Note](v2_stabilization_note_en.md) | Confirms Option B / Single-File Section Separation as the v2.0 stable baseline while preserving a one-JSON default flow and avoiding v1.x deprecation. It is a stabilization note toward the stable specification, not the specification itself, final schema, or validation standard. |
| [Stable Specification](v2_stable_specification_en.md) | Defines the converged v2.0 stable specification around Option B / Single-File Section Separation, preserving a one-JSON default flow and repositioning v1.x assets inside v2.0. It is not an exploratory design note, JSON Schema, validation standard, or required replacement for v1.x profiles, and does not deprecate v1.x. |
| [v2 Draft Template](../templates/pim-dbs_v2_draft.json) | Provides the current non-normative single-JSON draft template. |
| [Migration Guidance Note](v2_migration_guidance_note_en.md) | Explains optional migration from v1.x to the v2 draft without invalidating v1.x. |
| [Migration Checklist](v2_migration_checklist_en.md) | Provides a safety checklist for users who want to try optional v1.x to v2 draft migration. |
| [Preflight Guide](v2_preflight_guide_en.md) | Provides maintainer checks before updating, exposing, or preparing release links for v2 Draft / Preview materials. |

## 5. Design Notes

The design notes are exploratory documents.

They clarify intent before implementation:

- separating stable profile material from journal-like private context
- defining public template and private instance boundaries
- keeping real Dialogue Exemplars and private data out of public examples
- treating `charter` as operating principles rather than binding commands
- treating `calibration` as user-side verification and observation
- evaluating the balance between structural separation and a beginner-friendly single-file default
- stabilizing Option B / Single-File Section Separation as the v2.0 baseline direction
- defining the v2.0 stable specification without turning it into JSON Schema or a validation standard
- preserving the v1.x path

Note: The Stable Specification is not an exploratory design note; it is the converged v2.0 specification document. It is still not a JSON Schema, validation standard, or required replacement for v1.x profiles.

## 6. Examples

Examples are public-safe, fully fictional support documents for understanding the v2 Draft / Preview structure.

They do not make v2.0 a stable specification, final schema, validation standard, or required replacement for v1.x profiles:

- [Minimal Fictional Sample](v2_minimal_sample_fictional_en.md) is a fully fictional v2 worked example.
- [Fictional Migration Example](v2_migration_example_fictional_en.md) is a fully fictional migration example from a v1.x-style summary into the v2 draft structure.

## 7. Operational Guides

Operational guides are support documents for people using or maintaining the v2 Draft / Preview materials.

They do not make v2.0 a stable specification:

- [Migration Checklist](v2_migration_checklist_en.md) helps users try optional migration from v1.x to the v2 draft while keeping private-only material out of public files.
- [Preflight Guide](v2_preflight_guide_en.md) helps maintainers check safety, links, canonical-template preservation, and EN/JA consistency before exposing v2 materials more broadly.

## 8. Draft Template

The draft template is:

- a single JSON file
- non-normative
- not a final schema
- not a validation standard
- not a required replacement for v1.x

Current top-level sections:

- `meta`
- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

The v1.x canonical template is not changed by this draft.

## 9. What Is Not Included Yet

The current v2.0 materials do not include:

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- validation tooling
- migration helper
- README or CHANGELOG formal navigation
- tag or release

These may be considered later, but they are not part of the current v2 design set.

## 10. Safety Boundaries

Across all v2.0 materials:

- Do not claim AI consciousness, a soul, or real persistent AI memory.
- Do not publish real Dialogue Exemplars, real conversation logs, voiceprint-derived data, or private records.
- Do not mix public templates with private instances.
- Treat RCB as user-side observation of visible response changes, not measurement of AI internal state.
- Treat `calibration` as user-side verification and observation, not AI internal diagnosis.
- Keep System Loading Instruction below safety guidelines, platform terms, and higher-priority instructions.
- Do not treat v1.x as deprecated.

## 11. Suggested Next Steps

Possible next steps:

- review the index for missing v2 files
- decide whether v2 docs should remain internal-only for now
- review the draft template against the migration guidance
- prepare a future README link only after the v2 draft is stable enough
- decide whether JSON Schema, `probes.json`, or `packet.md` belongs in v2.0 or later
