# PIM-DBS v2 Draft Template Refinement Note

This document is a non-normative refinement note for the current PIM-DBS v2 Draft / Preview template.

It is not a v2.0 specification, not a final schema, not a validation standard, and not a required replacement for v1.x profiles. It does not change `templates/pim-dbs_v2_draft.json` by itself.

Related materials:

- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)
- [v2 Template Shape Note](v2_template_shape_note_en.md)
- [v2 Draft Template Decisions Note](v2_draft_template_decisions_en.md)
- [v2 Migration Checklist](v2_migration_checklist_en.md)
- [v2 Preflight Guide](v2_preflight_guide_en.md)
- [v2 Draft / Preview Index](v2_index_en.md)

## 1. Purpose

This note identifies possible improvements to `templates/pim-dbs_v2_draft.json` before editing the draft template itself.

The goal is to keep future edits small, reviewable, and safe:

- clarify draft status
- strengthen public/private separation
- improve human readability
- avoid language that looks like a final schema or validation standard
- preserve the current v1.x stable path

## 2. Current Draft Status

The current v2 draft template is:

- a non-normative draft
- not a final schema
- not a validation standard
- not a required replacement for v1.x profiles
- a single-JSON draft for review and experimentation

The v1.x canonical template, `templates/pim-dbs_template.json`, remains valid.

Public templates and private instances must remain separate. Public draft material should use placeholders, empty structures, or fully fictional examples only.

## 3. Refinement Principles

Future refinements should follow these principles:

The current draft already satisfies many of the safety requirements listed here. Refinement should therefore be incremental polishing, not a full rewrite.

- Keep each edit small and easy to review.
- Avoid wording that makes the draft look like a fixed schema.
- Strengthen public/private boundaries.
- Do not treat v1.x as deprecated.
- Keep real Dialogue Exemplars and private records out of public draft material.
- Treat RCB as user-side observation of visible response changes, not measurement of AI internal state.
- Treat `calibration` as user-side verification and observation, not AI internal diagnosis.
- Keep `system_loading_instruction` below higher-priority instructions, safety guidelines, and platform terms.

## 4. Candidate Refinements

Possible refinement targets:

| Area | Candidate refinement | Reason |
| --- | --- | --- |
| `meta` | Clarify draft status and draft notice. | Reduces the risk that the template is mistaken for a final schema. |
| `journal` | Make public placeholders and private-only notes clearer. | Helps prevent private material from being copied into public files. |
| `charter` | Improve readability of lightweight operating principles. | Keeps charter as boundaries and principles, not commands or contracts. |
| `calibration` | Strengthen wording around user-side verification and observation. | Prevents calibration from looking like AI internal diagnosis. |
| RCB references | Add or refine notes that RCB is not a fixed score store. | Keeps RCB aligned with response-change observation rather than model health scoring. |
| `system_loading_instruction` | Clarify safety, platform-term, and higher-priority instruction limits. | Reduces the risk of override-like interpretation. |
| `Family_Network` | Keep public draft usage to empty structures or private-only notes. | Avoids exposing real family or relationship data. |
| `Inside_Jokes` | Keep omitted from the public draft by default. | Avoids leaking private context through informal examples. |

These are candidates only. Each edit should be reviewed separately before changing the draft template.

## 5. Do Not Change Yet

Do not change the following as part of the first refinement pass:

- `templates/pim-dbs_template.json`
- the v1.x canonical structure
- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- validation tooling
- migration helper
- multi-file workflow
- real Dialogue Exemplars
- real conversation logs
- voiceprint-derived data
- private memories, family data, or relationship data

## 6. Deferred Items

The following should remain deferred unless a later release explicitly scopes them:

- formal JSON Schema
- validation tooling
- migration helper
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- optional multi-file private instance workflow
- expanded fictional public samples
- detailed calibration examples

These may be useful later, but adding them too early could make the draft look more final than it is.

## 7. Safety Checks Before Editing the Draft

Before editing `templates/pim-dbs_v2_draft.json`, confirm:

- [ ] `git status` is clean or all current changes are understood.
- [ ] `templates/pim-dbs_template.json` has no unintended diff.
- [ ] The v2 draft still parses as JSON after editing.
- [ ] The draft still says it is non-normative.
- [ ] The draft still says it is not a final schema.
- [ ] The draft still says it is not a validation standard.
- [ ] The draft still says it is not a required replacement for v1.x profiles.
- [ ] Public draft content does not contain real Dialogue Exemplars, real conversation logs, voiceprint-derived data, or private records.
- [ ] `journal` public content remains empty, placeholder-based, or fully fictional.
- [ ] RCB is not represented as a fixed long-term score.
- [ ] `calibration` is not described as AI internal diagnosis.
- [ ] `system_loading_instruction` does not override higher-priority instructions, safety guidelines, or platform terms.

## 8. Relationship to Migration Checklist

The [v2 Migration Checklist](v2_migration_checklist_en.md) is user-facing operational support for people trying optional migration from v1.x to the v2 draft.

Refinement changes should make that checklist easier to follow. They should not force users to migrate or imply that v1.x profiles are obsolete.

## 9. Relationship to Preflight Guide

The [v2 Preflight Guide](v2_preflight_guide_en.md) should be used before exposing refined v2 materials more broadly.

If the draft template is edited, the preflight should confirm:

- link integrity
- EN/JA consistency
- v1.x canonical template preservation
- public/private safety
- risk-wording safety
- release-readiness wording, if release notes are prepared

## 10. Open Questions

Open questions for later review:

- Should the next draft edit focus on `meta`, `journal`, or `calibration` first?
- Should `Family_Network` remain present as an empty structure, or move fully to private-only guidance?
- Should `Inside_Jokes` stay omitted from public drafts in all cases?
- How much RCB guidance belongs inside the draft versus linked external guides?
- Should future fictional samples include more calibration examples without implying internal diagnosis?
- When, if ever, should the project create JSON Schema?
