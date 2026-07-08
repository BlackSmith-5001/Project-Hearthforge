# PIM-DBS v2.0 Publication Gate Note

This is an internal publication gate note for the current PIM-DBS v2.0 design materials.

It is not a release plan, not a v2.0 specification, and not a decision to publish the v2 materials through README or CHANGELOG. It exists to decide whether the v2 design set should remain internal, become quietly discoverable, or be presented as a draft / preview.

## 1. Purpose

The v2.0 design set now includes concept notes, mapping notes, public example guidance, a fictional sample, template shape decisions, migration guidance, an internal index, and a non-normative draft template.

Before adding README or CHANGELOG links, this note records:

- what v2 assets currently exist
- what publication options are available
- which safety preconditions must remain visible
- what should not be published yet
- what to check before exposing the v2 materials more broadly

## 2. Current v2 Assets

Current v2-related assets:

- [v2 Concept Study](v2_concept_study_en.md)
- [v2 Field Mapping Note](v2_field_mapping_note_en.md)
- [v2 Public Example Design Note](v2_public_example_design_note_en.md)
- [v2 Minimal Fictional Sample](v2_minimal_sample_fictional_en.md)
- [v2 Template Shape Note](v2_template_shape_note_en.md)
- [v2 Draft Template Decisions Note](v2_draft_template_decisions_en.md)
- [v2 Migration Guidance Note](v2_migration_guidance_note_en.md)
- [v2 Internal Index](v2_index_en.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)

These assets are design and review materials unless a later release explicitly promotes them.

## 3. Publication Options

| Option | Description | Benefit | Risk |
| --- | --- | --- | --- |
| A. Keep internal for now | Do not add README or CHANGELOG links yet. | Lowest risk; keeps v2 review private to maintainers and close collaborators. | Harder for external reviewers to find the v2 work. |
| B. Add only v2 index as a quiet internal reference | Link only the internal index from a low-emphasis location. | Gives one controlled entry point without presenting v2 as final. | Readers may still treat the index as a public roadmap. |
| C. Add a README section labeled v2 Draft / Preview | Add a clearly labeled draft section to README. | Makes v2 review easier for interested readers. | Could be mistaken for a v2.0 release unless wording is very clear. |
| D. Create a formal release such as v1.7.0 with v2 draft notes | Release the v2 notes as a v1.x preview release. | Clear versioned checkpoint while preserving v1.x. | Requires careful release notes to avoid implying replacement. |
| E. Jump to v2.0-preview | Publish as an explicit preview line. | Signals major structural work. | Highest risk of being mistaken for a stable v2.0 specification. |

## 4. Recommended Option

Do not treat the current materials as a formal v2.0 release yet.

The safest direction is to keep v1.x as the active canonical path and evaluate a cautious v2 Draft / Preview exposure. If exposed, the first public entry should probably be the v2 index, with repeated labels such as:

- non-normative draft
- preview
- not final schema
- not a v1.x replacement
- public/private safety boundary applies

This note does not make the final publication decision.

If a versioned release is chosen, a v1.x release such as v1.7.0 is safer than v2.0-preview at this stage, because it keeps v1.x as the stable line while presenting v2 materials as draft / preview work.

## 5. README Exposure Options

Possible README exposure levels:

1. No README link yet.
2. Add a quiet Reference link to the v2 index.
3. Add a small "v2 Draft / Preview" section below the stable v1.x usage path.
4. Add a more visible v2 section only after the draft template and migration guidance have been reviewed again.

If README exposure happens, the stable v1.x flow should remain first. v2 should not appear to replace the current template, guides, examples, or Guild Master Demo.

## 6. CHANGELOG / Versioning Options

Possible versioning choices:

- no CHANGELOG entry yet
- add a future "v2 design materials" note under an unreleased v1.x section
- create a v1.x release that explicitly says the v2 materials are draft / preview only
- reserve `v2.0-preview` for a later checkpoint

Any CHANGELOG entry should say that:

- v1.x remains valid
- the v2 draft is optional
- the v2 draft is not a final schema
- the v2 draft is not a validation standard
- the v2 draft is not a required replacement

## 7. Safety Preconditions

Before exposing v2 materials more broadly, the following must remain true:

- the v1.x canonical template remains valid
- the v2 draft is labeled as a non-normative draft
- the v2 draft is not described as a final schema
- the v2 draft is not described as a validation standard
- the v2 draft is not described as a v1.x replacement
- public templates and private instances are not mixed
- real Dialogue Exemplars, real conversation logs, voiceprint-derived data, and private records are not published
- public `journal` material is empty, placeholder-only, or fully fictional
- RCB is not described as measurement of AI internal state
- `calibration` is not described as AI internal diagnosis
- `system_loading_instruction` does not override higher-priority instructions, safety guidelines, or platform terms

## 8. What Must Remain Clear

Readers should be able to understand that:

- PIM-DBS does not claim AI consciousness, a soul, or real persistent AI memory
- the v2 structure is about safer separation of user-side context
- `journal` is privacy-sensitive
- `charter` is an operating-principles area, not a contract or safety override
- `calibration` is a user-side verification and observation layer
- public examples must be blank, generic, sanitized, or fully fictional
- private instance material should not be turned into public sample data

## 9. What Not to Publish Yet

Do not publish or present the following as part of the current v2 set:

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- migration helper
- validation tooling
- private instance examples
- real Dialogue Exemplars
- real family or relationship data
- real conversation logs
- voiceprint-derived data

These may be explored later, but they are not ready for public-facing v2 navigation.

## 10. Preflight Checklist

Before adding README or CHANGELOG links:

- Confirm there is no diff in the v1.x canonical template.
- Confirm the v2 draft JSON parses successfully.
- Confirm all v2 index links resolve.
- If adding README exposure, label the section Draft / Preview / non-normative.
- If adding CHANGELOG exposure, state that v2 is not a v1.x replacement.
- Confirm v2-related files contain no private-only data.
- Confirm RCB, `calibration`, and `system_loading_instruction` safety boundaries remain intact.
- Confirm public examples use only blank, placeholder, generic, sanitized, or fully fictional content.
- Confirm no release tag is implied by the documentation alone.
- Confirm that risk-related terms such as measurement, diagnosis, consciousness, override, soul, memory, and internal state appear only in negating, limiting, or safety-framing contexts.
- Confirm EN/JA consistency for newly exposed files, including headings, tables, links, and safety notes.

## 11. Open Questions

Open questions before publication:

- Should the v2 materials remain internal until one more review pass?
- Should the first public link be only the v2 index?
- Should v2 exposure be tied to a v1.x release such as v1.7.0?
- Should `v2.0-preview` be reserved for a more polished checkpoint?
- How much README visibility is useful without confusing first-time users?
- Should external reviewers see the draft template before or after reading the migration guidance?
