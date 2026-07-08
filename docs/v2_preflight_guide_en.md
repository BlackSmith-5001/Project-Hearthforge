# PIM-DBS v2 Preflight Guide

This guide is for maintainers who update, expose, or prepare release links for PIM-DBS v2 Draft / Preview materials.

It is part of the v2 Draft / Preview support materials. It is not a v2.0 specification, not a final schema, not a validation standard, and not a required replacement for v1.x profiles.

Use this before adding or changing README, CHANGELOG, release notes, or other public entry points for v2-related files.

Related materials:

- [v2 Publication Gate Note](v2_publication_gate_note_en.md)
- [v2 Migration Checklist](v2_migration_checklist_en.md)
- [v2 Draft / Preview Index](v2_index_en.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)

## 1. Purpose

This preflight guide helps maintainers check safety, link integrity, canonical-template preservation, and EN/JA consistency before exposing v2 Draft / Preview materials more broadly.

It is different from the migration checklist:

- The Migration Checklist is for users trying an optional v1.x to v2 draft migration.
- This Preflight Guide is for maintainers preparing public links, release notes, or repository updates.

## 2. When to Run This Preflight

Run this preflight before:

- adding README or README_JA links to v2 materials
- adding CHANGELOG entries for v2 Draft / Preview work
- publishing release notes that mention v2 materials
- editing `templates/pim-dbs_v2_draft.json`
- adding new v2 design notes
- changing safety wording around RCB, calibration, or system loading instructions

Run a lighter version after small typo fixes if the file is already publicly linked.

## 3. Preflight Scope

Check the files affected by the current change and any linked v2 files that may become newly visible.

Common scope:

- `README.md`
- `README_JA.md`
- `CHANGELOG.md`
- `docs/v2_*.md`
- `templates/pim-dbs_v2_draft.json`
- `templates/pim-dbs_template.json`

Do not treat this guide as a substitute for human review.

## 4. Repository Safety Checks

- [ ] `git status` is clean before starting, or all existing changes are understood.
- [ ] The changed files match the intended scope.
- [ ] No unrelated files are staged.
- [ ] `git diff --check` passes.
- [ ] If release labels are being updated, the target commit is identified before tagging.
- [ ] CHANGELOG version headings are not duplicated.
- [ ] README / README_JA / CHANGELOG changes do not accidentally promote v2 to stable status.

## 5. v1.x Stable Path Checks

- [ ] `templates/pim-dbs_template.json` has no unintended diff.
- [ ] README still presents the v1.x stable flow before v2 Draft / Preview material.
- [ ] v1.x is not described as deprecated.
- [ ] v2 draft materials are not described as required replacements for v1.x profiles.
- [ ] Release notes, if prepared, say that v1.x remains the current stable profile path.

## 6. v2 Draft Template Checks

- [ ] `templates/pim-dbs_v2_draft.json` parses as JSON.
- [ ] The v2 draft labels itself as non-normative.
- [ ] The v2 draft says it is not a final schema.
- [ ] The v2 draft says it is not a validation standard.
- [ ] The v2 draft says it is not a required replacement for v1.x.
- [ ] The v2 draft does not use strict JSON Schema-style validation language.
- [ ] The v2 draft keeps nesting shallow enough for humans to review.
- [ ] The v2 draft does not introduce private-only data into public template material.

## 7. Public / Private Data Checks

- [ ] Public files do not contain real Dialogue Exemplars.
- [ ] Public files do not contain real conversation logs.
- [ ] Public files do not contain voiceprint-derived style data.
- [ ] Public files do not contain private records, private memories, or relationship history.
- [ ] Public files do not contain medical, workplace, address, real-name, family, or internal relationship details.
- [ ] `journal` examples in public files are empty structures, placeholders, or fully fictional examples only.
- [ ] Any fictional examples are clearly fictional.
- [ ] Public examples do not look like real profiles with names changed.
- [ ] Private instance content is not mixed into public template examples.

## 8. Link Checks

- [ ] Markdown relative links resolve from the file where they appear.
- [ ] README / README_JA links, if added, use `docs/v2_index_en.md` and `docs/v2_index_ja.md` as the main entry points.
- [ ] README does not list every individual v2 note when a single index link is enough.
- [ ] v2 index links point to existing files.
- [ ] EN and JA versions point to the matching language file when available.
- [ ] Links to `../templates/pim-dbs_v2_draft.json` resolve correctly from `docs/`.

## 9. EN/JA Consistency Checks

- [ ] EN and JA files have corresponding headings.
- [ ] Tables, if present, have corresponding columns and rows.
- [ ] Safety notes appear in both languages.
- [ ] Links are present in both languages and point to the correct localized file.
- [ ] Terms such as v2 Draft / Preview, public template, private instance, RCB, calibration, and system loading instruction are used consistently.
- [ ] The JA version is natural Japanese, not only a mechanical translation.

## 10. Risk Wording Checks

- [ ] Risk-related terms such as measurement, diagnosis, consciousness, override, soul, memory, and internal state appear only in negating, limiting, or safety-framing contexts.
- [ ] The text does not claim AI consciousness.
- [ ] The text does not claim an AI soul.
- [ ] The text does not claim persistent or real AI memory.
- [ ] The text does not say that user profiles override safety rules or platform terms.
- [ ] The text does not describe RCB as a precise metric or hidden-state measurement.
- [ ] The text does not ask AI to self-report internal load, fatigue, emotion, or health.

## 11. RCB / Calibration / System Loading Instruction Checks

- [ ] RCB is described as user-side observation of visible response changes.
- [ ] RCB is not described as measuring AI internal state.
- [ ] RCB is not stored as a fixed long-term health score.
- [ ] Calibration is described as user-side verification and observation.
- [ ] Calibration is not described as AI internal diagnosis or model health measurement.
- [ ] System loading instruction is described as conversation guidance.
- [ ] System loading instruction does not override higher-priority instructions.
- [ ] System loading instruction does not override safety guidelines or platform terms.
- [ ] System loading instruction does not tell the assistant to claim memories that are not in the profile.

## 12. Release Readiness Checklist

- [ ] The intended release scope is clear.
- [ ] The target commit for tag or release is identified.
- [ ] The CHANGELOG entry uses the correct version and date.
- [ ] Release notes do not call v2 materials a stable v2.0 specification.
- [ ] Release notes say v2 materials are draft / preview if they mention them.
- [ ] README / README_JA still keep the stable v1.x path visible.
- [ ] All relative links added in the release have been checked.
- [ ] EN/JA files added or exposed in the release have been compared.
- [ ] No JSON Schema, `probes.json`, `packet.md`, migration helper, or Guild Master Demo v2 support is implied unless actually added.
- [ ] The final `git status` is clean before tagging.

## 13. What This Guide Does Not Do

This guide does not:

- make v2.0 a stable specification
- replace the v1.x canonical template
- create JSON Schema
- create `probes.json`
- create `packet.md`
- update Guild Master Demo
- validate private instances
- approve publishing private data
- guarantee that a release is safe without human review
