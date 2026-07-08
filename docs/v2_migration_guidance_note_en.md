# PIM-DBS v2.0 Migration Guidance Note

This is a non-normative migration guidance note. It explains one possible way to move from a v1.x single-JSON profile toward the v2.0 draft structure, but it is not a final schema, validation standard, or required migration path.

PIM-DBS v1.x profiles remain valid. The v2.0 draft is an optional structure for users who want clearer separation between public templates, private instances, stable profile data, journal-like context, operating principles, and user-side verification.

## 1. v1.x Is Still Valid

The v1.x single-JSON template remains a valid PIM-DBS format.

Users do not need to rewrite existing profiles just because a v2.0 draft exists. A working v1.x profile can remain in use, especially when it is already clear, private, and easy to reload.

The v2.0 draft should be treated as a structural option, not a replacement order.

## 2. v2 Draft Is Optional

The v2.0 draft is for users who want to separate different kinds of profile material:

- stable identity and response style
- private or episode-like context
- operating principles and boundaries
- user-side restoration checks and observation notes

It is not a final schema. It should not be treated as a strict validation standard.

## 3. Who May Want to Migrate

Migration may help users who:

- maintain larger profiles that have become hard to scan
- want a clearer boundary between public template material and private instance data
- need to separate stable persona settings from private journal-like context
- use Restoration Verification, Model Notes, Temporal Anchor, or RCB notes regularly
- want to prepare for future v2.0 structure experiments without abandoning v1.x

## 4. Who Should Stay on v1.x

Staying on v1.x is reasonable when:

- the current single-JSON profile is small and understandable
- the profile is only used privately by one person
- there is no need to publish a public template
- the user does not need separate journal, charter, or calibration areas yet
- migration would add more confusion than clarity

v1.x is not deprecated by this note.

## 5. Field Mapping Overview

This table is a practical overview, not a final mapping rule.

| v1.x field or concept | Possible v2 draft area | Migration note |
| --- | --- | --- |
| `Meta_Information` | `meta` | Use `meta` for draft status, version notes, privacy level, and compatibility notes. |
| Identity, name, role, basic profile | `core` | Keep stable public-safe identity here. |
| Voice, tone, speaking style | `core` | Use generic or fictional style notes in public templates. Real voiceprint-derived style data should not be migrated into public files; keep it private-only. |
| Cognitive Framework / TCF | `core` | Treat as a lightweight descriptive subsection candidate, not an internal AI-state claim. |
| Values, boundaries, user-facing principles | `charter` | Use as operating principles, not commands that override safety rules. |
| Provenance | `journal` or `calibration` | Keep provenance labels wherever recorded context or verification notes need source clarity. |
| Shared Episodes / contextual profile | `journal` | Public drafts should use empty structures, placeholders, or fully fictional examples only. |
| Dialogue Exemplars | `journal` | Real exemplars are private-only. Public drafts should use only fictional examples. |
| Family Network | `journal` | Public drafts should keep this empty or mark it private-only. |
| Inside Jokes | Do not migrate into public files by default | Omit from public drafts unless fully fictional and harmless. |
| Restoration Verification | `calibration` | User-side checks of reconstructed response style, not hidden memory tests. |
| Model Notes | `calibration` | Use sanitized, generic, or fictional notes in public files. |
| Temporal Anchor | `calibration` | A user-provided session reference, not persistent AI memory. |
| Response Change Catalog | `calibration` reference | Reference observed response changes when useful. |
| Response Change Bands / RCB | `calibration` reference or observation notes | Do not store a fixed score. Do not ask the AI to self-report RCB. |
| System Loading Instruction | `system_loading_instruction` | Keep as guidance that does not override safety rules, platform terms, or higher-priority instructions. |

## 6. Step-by-Step Migration

1. Keep the original v1.x profile unchanged as a fallback.
2. Create a separate v2 draft copy instead of editing the only working file.
3. Move version, draft, privacy, and compatibility notes into `meta`.
4. Move stable identity, role, tone, and response-style notes into `core`.
5. Move operating principles and boundaries into `charter`.
6. Before moving anything into `journal`, decide whether it is public-safe or private-only.
7. Move Restoration Verification, Model Notes, Temporal Anchor notes, and RCB references into `calibration` only when they are useful.
8. Rewrite the System Loading Instruction so it clearly says the profile is guidance and does not override safety guidelines, platform terms, or higher-priority instructions.
9. Review the draft for private information before sharing it.
10. Keep the v1.x file available until the v2 draft has been tested in normal use.

## 7. Public Template vs Private Instance

A public template is a blank, generic, or fully fictional file that helps other users understand the structure.

A private instance is a filled profile that may contain personal context, private interaction history, real dialogue snippets, relationship-specific notes, or sensitive details.

Migration should never turn a private instance into a public template by accident. When unsure, keep the material private.

## 8. What Not to Migrate Into Public Files

Do not migrate the following into public v2 draft files:

- real Dialogue Exemplars
- real conversation logs
- voiceprint-derived or real-person speech pattern data
- private memories, relationship history, or personal episodes
- real names, addresses, workplace details, medical details, family circumstances, or internal relationship notes
- non-public family or relations data
- inside jokes that reveal private context
- AI-claimed memories that the user has not verified
- material that makes the profile look like a claim of AI consciousness, a soul, or persistent internal memory

These may belong in a private instance if the user intentionally keeps them, but they should not be part of a public template.

## 9. RCB / Calibration Migration Notes

`calibration` is a user-side verification and observation area.

It may include:

- Restoration Verification probes
- expected response features
- failure signals
- Model Notes
- Temporal Anchor usage notes
- references to Response Change Bands / RCB guidance
- user-side observation notes about visible response changes

It should not diagnose AI internals. RCB does not measure AI cognition, fatigue, emotion, consciousness, hidden memory, model health, or real internal state.

Avoid storing a permanent RCB score in the profile. RCB should remain a coarse, session-local observation method that helps the user choose a low-risk next step.

## 10. System Loading Instruction Notes

The v2 draft keeps System Loading Instruction as its own section.

It should say that the profile describes desired conversation style, continuity context, and operating preferences.

It should also say that the profile does not:

- override safety guidelines
- override platform terms
- override higher-priority system or developer instructions
- prove that the AI has internal memory, consciousness, or a soul
- permit the assistant to claim memories not present in the profile or current conversation

## 11. Common Mistakes

Common migration mistakes include:

- treating v2 draft as a mandatory replacement for v1.x
- deleting the v1.x fallback too early
- publishing private journal content
- moving real Dialogue Exemplars into a public file
- publishing a real profile with only names changed, while the person or relationship remains identifiable
- treating `calibration` as AI diagnosis
- storing RCB as a fixed health score
- asking the AI to self-report its RCB level
- making the System Loading Instruction sound like it overrides safety rules or platform terms
- mixing public placeholders with private relationship history in the same shareable file
- treating the v2 draft as a final schema

## 12. Open Questions

Open questions for later v2.0 work:

- How much v1.x naming should remain for migration comfort?
- Should v2.0 provide a separate migration checklist?
- Should a future Guild Master flow export both v1.x and v2 draft formats?
- How should private instances be organized without encouraging public sharing?
- When should JSON Schema, `probes.json`, or `packet.md` be introduced, if at all?
- How much example content can be included without making users think private journal data should be published?
