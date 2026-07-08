# PIM-DBS v2 Migration Checklist

This checklist is for users who want to try moving a v1.x PIM-DBS profile into the v2 draft structure.

It is part of the v2 Draft / Preview materials. It is non-normative, not a final schema, not a validation standard, and not a required replacement for v1.x profiles.

The v1.x profile format remains valid. Use this checklist only if separating material into `core`, `journal`, `charter`, `calibration`, and `system_loading_instruction` would make your profile easier to maintain.

Related materials:

- [v2 Migration Guidance Note](v2_migration_guidance_note_en.md)
- [v2 Field Mapping Note](v2_field_mapping_note_en.md)
- [v2 Public Example Design Note](v2_public_example_design_note_en.md)
- [v2 Draft / Preview Index](v2_index_en.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)

## 1. Purpose

Use this checklist to migrate carefully without turning private instance data into public template material.

The goal is not to make a perfect v2.0 profile. The goal is to test whether the v2 draft structure helps separate stable profile data, private context, operating principles, and user-side verification notes.

If you only want a quick first pass, start with Section 2, Section 4, and Section 10 before working through the full checklist.

## 2. Before You Start

- [ ] Make a copy of the original v1.x profile before editing.
- [ ] Confirm that the original v1.x profile remains valid and usable.
- [ ] Decide whether this migration is for a public template or a private instance.
- [ ] Read the v2 Migration Guidance Note before moving fields.
- [ ] Review the v2 Field Mapping Note for likely section placement.
- [ ] Review the v2 Public Example Design Note before publishing anything.
- [ ] Keep the v1.x profile available as a fallback.
- [ ] Do not treat the v2 draft as a final schema or validation standard.

## 3. Migration Checklist

- [ ] Identify which v1.x fields belong in `meta`.
- [ ] Identify stable identity, role, tone, and style material for `core`.
- [ ] Identify private, episode-like, or relationship-specific material for `journal`.
- [ ] Identify operating principles and boundaries for `charter`.
- [ ] Identify verification, model notes, Temporal Anchor notes, or RCB references for `calibration`.
- [ ] Identify the current loading instruction and rewrite it for `system_loading_instruction`.
- [ ] Move only public-safe material into public files.
- [ ] Keep private-only material in a private instance.
- [ ] Avoid renaming sections in a way that makes the draft look like a final schema.
- [ ] Parse the draft JSON after editing if you are working in JSON.

## 4. Public / Private Separation Checklist

- [ ] Confirm whether the file is meant to be public or private.
- [ ] Do not mix public template placeholders with private instance history.
- [ ] Do not publish real Dialogue Exemplars.
- [ ] Do not publish real conversation logs.
- [ ] Do not publish voiceprint-derived or real-person speech pattern data.
- [ ] Do not publish private memories, private records, or relationship history.
- [ ] Do not publish medical, workplace, address, real-name, family, or internal relationship details.
- [ ] Do not publish inside jokes that reveal private context.
- [ ] Do not publish AI-claimed memories that the user has not verified.
- [ ] When unsure, keep the material private.

## 5. Core Checklist

- [ ] Keep `core` focused on stable identity, role, purpose, and general style.
- [ ] Use generic or fully fictional style descriptions in public templates.
- [ ] Keep real voiceprint-derived style data private-only.
- [ ] Keep private relationship history out of public `core`.
- [ ] Treat cognitive framework notes as user-side descriptions, not AI internal-state claims.
- [ ] Keep `core` readable and not overly nested.

## 6. Journal Checklist

- [ ] Treat `journal` as privacy-sensitive.
- [ ] For public templates, use an empty structure, placeholders, or fully fictional examples only.
- [ ] Keep real episodes, private memories, and relationship history in private instances.
- [ ] Use provenance labels when recording source-sensitive context.
- [ ] Do not include real Dialogue Exemplars in public `journal`.
- [ ] Do not include real family or relationship data in public `journal`.
- [ ] Do not make the public `journal` look like a private memory archive.

## 7. Charter Checklist

- [ ] Use `charter` for operating principles and boundaries.
- [ ] Do not present `charter` as a contract that binds the AI.
- [ ] Do not present `charter` as a command layer or system prompt.
- [ ] Do not use `charter` to override safety guidelines, platform terms, or higher-priority instructions.
- [ ] Keep public `charter` examples general, fictional, or sanitized.
- [ ] Include boundaries that make public/private handling clear.

## 8. Calibration Checklist

- [ ] Treat `calibration` as user-side verification and observation.
- [ ] Do not treat `calibration` as AI internal diagnosis.
- [ ] Do not treat `calibration` as model health measurement.
- [ ] Put Restoration Verification probes here when useful.
- [ ] Put Model Notes here only if they are generic, sanitized, fictional, or private.
- [ ] Put Temporal Anchor notes here as user-provided session references.
- [ ] Reference RCB as a guide for visible response changes.
- [ ] Do not store a fixed RCB score.
- [ ] Do not ask the AI to self-report its RCB level.

## 9. System Loading Instruction Checklist

- [ ] State that the profile is user-provided context and guidance.
- [ ] State that the profile does not override safety guidelines.
- [ ] State that the profile does not override platform terms.
- [ ] State that the profile does not override higher-priority system or developer instructions.
- [ ] State that the assistant should not claim memories, internal states, consciousness, emotions, or private history not provided by the user.
- [ ] If time context is uncertain, instruct the assistant to ask the user instead of inventing missing temporal context.
- [ ] Keep the instruction concise enough to reload safely.

## 10. Final Safety Review

- [ ] Confirm that the original v1.x profile still exists.
- [ ] Confirm that the v2 draft is labeled as draft / preview / non-normative.
- [ ] Confirm that the v2 draft is not described as a final schema.
- [ ] Confirm that the v2 draft is not described as a validation standard.
- [ ] Confirm that the v2 draft is not described as a required replacement for v1.x.
- [ ] Confirm that public files contain no private-only data.
- [ ] Confirm that RCB is not described as AI internal-state measurement.
- [ ] Confirm that `calibration` is not described as AI internal diagnosis.
- [ ] Confirm that `system_loading_instruction` does not override safety guidelines, platform terms, or higher-priority instructions.
- [ ] Confirm EN/JA consistency if both language versions are being published.

## 11. What This Checklist Does Not Do

This checklist does not:

- create a v2.0 stable specification
- create JSON Schema
- create `probes.json`
- create `packet.md`
- validate a profile automatically
- migrate private data safely by itself
- make v2 draft mandatory
- deprecate v1.x
- authorize publication of private instances
