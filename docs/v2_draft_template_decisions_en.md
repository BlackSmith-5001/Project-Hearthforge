# PIM-DBS v2.0 Draft Template Decisions Note

This document is a non-normative provisional decisions note. It records temporary decisions for a possible PIM-DBS v2.0 draft template before any template file is created.

It is not a v2.0 draft template, JSON Schema, `probes.json`, `packet.md`, or implementation plan. These decisions may change after review.

## 1. Purpose

The purpose of this note is to reduce ambiguity before creating a v2.0 draft template.

It follows the v2.0 Template Shape Note and gives provisional decisions for the first draft only.

## 2. Decision Summary

| Item | Provisional decision |
| --- | --- |
| Template form | Start with a single JSON draft template. |
| Top-level sections | Use `meta`, `core`, `journal`, `charter`, `calibration`, and `system_loading_instruction` as candidates. |
| Metadata | Use an independent `meta` section. |
| v1.x `Meta_Information` | Treat as historical v1.x naming; move toward `meta` in the v2 draft. |
| Charter | Treat as a lightweight required-section candidate. |
| Calibration | Treat as a recommended-section candidate. |
| Journal in public draft | Use empty structure or fully fictional examples only. |
| Cognitive Framework / TCF | Consider a lightweight `core.cognitive_framework` subsection, not a top-level section. |
| RCB | Do not store fixed RCB scores; use guide references and observation notes only. |
| RCB paths | Treat dotted paths as illustrative paths, not final keys. |
| System Loading Instruction | Use a dedicated section with safety and platform-term limits. |
| Draft labeling | The draft template should include a clear non-normative draft note and avoid language that makes it look like a final schema or validation standard. |
| Family Network | Keep only as an empty structure or private-only note in the public draft. |
| Inside Jokes | Omit from the public draft by default. |
| Dialogue Exemplars | Use fully fictional examples only in public drafts. |
| Model Notes | Use fictional or generic examples only inside `calibration`. |
| v1.x compatibility | Do not invalidate v1.x single-JSON profiles. |
| Deferred tooling | Move JSON Schema, `probes.json`, `packet.md`, and Guild Master Demo v2 support to v2.1 or later. |

## 3. Top-level Sections

The first v2.0 draft template should use this provisional top-level shape:

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

These are candidate section names, not final schema keys.

## 4. Metadata Decision

Use `meta` as an independent top-level section.

Rationale:

- metadata is not persona identity
- `core` should stay focused on profile content
- future versioning can separate protocol version, draft/schema version, and profile version

`Meta_Information` should be described as historical v1.x naming. The v2 draft can mention the mapping, but the draft shape should move toward `meta`.

## 5. Core and Cognitive Framework

`core` should hold stable profile material:

- identity
- role
- purpose
- tone
- speaking style
- non-private continuity cues

`Cognitive_Framework` / TCF should not become a separate top-level section in the first draft. A lightweight `core.cognitive_framework` subsection may be used if needed.

TCF should describe user-requested interaction patterns and response framing, not AI internal cognition.

## 6. Journal Decision

`journal` should remain a top-level candidate, but public drafts must keep it safe.

Public drafts may include:

- empty structure
- placeholders
- a fully fictional short example
- private-only notes

Public drafts must not include real Dialogue Exemplars, real conversations, voiceprint-derived data, private records, real relationship history, real family data, medical context, workplace context, addresses, or real names.

## 7. Charter Decision

`charter` should be treated as a lightweight required-section candidate.

It should include:

- operating principles
- boundaries
- public/private handling
- safety reminders

The charter is not a contract, command layer, system prompt, or override of safety guidelines, platform terms, or higher-priority instructions.

## 8. Calibration Decision

`calibration` should be treated as recommended, not strictly required.

It may include:

- Restoration Verification
- Model Notes
- Temporal Anchor usage
- Response Change Catalog references
- RCB guide references and observation notes

Calibration is not AI internal diagnosis. It is a user-side verification and observation layer.

## 9. RCB Decision

RCB should not be stored as a fixed score in the template.

Use RCB as:

- a guide reference
- an observation note area
- a user-side response planning aid

Possible illustrative paths:

```text
calibration.response_change_bands.reference
calibration.response_change_bands.observation_notes
calibration.response_change_bands.user_side_responses
```

These dotted paths are illustrative paths, not final keys.

RCB is not a measurement of AI internal state, cognition, fatigue, emotion, consciousness, hidden memory, or model health. Do not ask the AI to self-report RCB.

## 10. System Loading Instruction Decision

`system_loading_instruction` should be a dedicated top-level section.

It should state:

- this is user-provided context
- it describes desired conversation style and boundaries
- it does not override safety guidelines, platform terms, or higher-priority instructions
- the assistant should not claim memories or internal states not present in the profile
- uncertain time context should be confirmed with the user

## 11. Public-only Restrictions

For a public v2 draft, keep the following restricted:

- `Family_Network`: blank, fictional, or private-only note
- `Inside_Jokes`: excluded by default, or fully fictional and lightweight
- `Dialogue_Exemplars`: fully fictional only
- `Model_Notes`: fictional or generic only
- `journal`: empty or fictional only

Do not mix public templates with private instances.

Safety defaults:

- `Inside_Jokes`: omit from the public draft by default.
- `Family_Network`: keep only as an empty structure or private-only note in the public draft.

## 12. v1.x Compatibility

v2.0 should not invalidate v1.x single-JSON profiles.

The v2 draft should be described as:

- a non-mandatory structural proposal
- a migration-friendly draft
- a clearer separation model
- not a forced replacement for v1.x

Existing users should not be required to split their profiles immediately.

## 13. Deferred Items

Move the following to v2.1 or later:

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- migration helper
- validation tooling
- multi-file public/private workflow

These should wait until the v2 draft structure has been reviewed.

## 14. Still Open

The items below are structural or naming-level open questions; they do not override the public/private safety decisions already listed above.

The following remain open for review:

- final key names
- exact nesting depth
- whether `journal` should include one fictional example or only placeholders
- whether `Inside_Jokes` should appear at all in the public draft
- whether `Family_Network` should be renamed or minimized
- how much v1.x naming should remain for migration comfort
- how much example content is enough without making the draft look like a private instance
