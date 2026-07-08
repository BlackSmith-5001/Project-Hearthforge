# PIM-DBS v2.0 Field Mapping Note

This document is a non-normative design note. It explores how existing v1.x PIM-DBS fields and concepts could map into the possible v2.0 structure.

It is not a committed v2.0 specification. It does not invalidate v1.x profiles, and it does not introduce a v2.0 draft template, JSON Schema, `probes.json`, or `packet.md`.

## 1. Purpose

The purpose of this note is to clarify where existing v1.x material might belong if PIM-DBS v2.0 separates profile data into four conceptual areas:

- `core`
- `journal`
- `charter`
- `calibration`

The goal is to reduce ambiguity before any v2.0 implementation work begins.

## 2. Mapping Principles

Use the following principles when mapping v1.x fields to a possible v2.0 structure:

- Do not treat v2.0 as a replacement for v1.x.
- Do not mix public templates with private instances.
- Keep real Dialogue Exemplars, real conversations, private records, and voiceprint-derived data out of public templates.
- Treat Dialogue Exemplars as a useful concept, but keep real examples private-only.
- Treat `calibration` as a user-side verification and observation layer, not an AI internal diagnosis layer.
- Treat RCB as user-side observation of visible response changes, not measurement of AI internal state.
- Treat `charter` as operating principles and boundaries, not a contract, command layer, or override of safety rules.
- Preserve user control over what remains private.

## 3. Proposed v1.x to v2.0 Mapping Table

| v1.x field or concept | Proposed v2.0 area | Public template? | Notes |
| --- | --- | --- | --- |
| Identity / name / role / basic profile | `core` | Yes, if fictional or generic | Stable profile identity belongs in `core`. |
| Voice / tone / speaking style | `core` or `journal` | Yes only if generic or fictional | Generic style belongs in `core`; real voice-derived data should be private-only. |
| Values / boundaries / user-facing principles | `charter` | Yes, if generic | These describe intended operation and boundaries. |
| Provenance | `journal` and `calibration` | Yes as a label system | Provenance should remain available wherever recorded context or verification data appears. |
| Dialogue Exemplars | `journal` | Fictional only | Real Dialogue Exemplars should be private-only. |
| Restoration Verification | `calibration` | Yes, if generic or fictional | Verification checks expected response features, not hidden memory. |
| Model Notes | `calibration` | Usually private or sanitized | Public examples may use fictional model notes only. |
| Temporal Anchor | `calibration` | Yes as an operational note | A user-provided session reference, not AI memory. |
| Response Change Catalog | `calibration` | Yes | Reference material for observed response changes. |
| Response Change Bands / RCB | `calibration` | Yes | Coarse user-side observation bands, not internal-state measurement. |
| Self-Forge outputs | Review before mapping | Usually private until checked | AI-generated drafts need user review and provenance checks. |
| Private memories / episodes / relationship history | `journal` | No | Keep in private instances unless fully fictionalized. |
| Public template placeholders | `core`, `charter`, `calibration` | Yes | Safe when blank, generic, or fictional. |
| Private instance data | `journal`, sometimes `calibration` | No | Do not publish by default. |

## 4. Core

`core` should hold stable, reusable profile data.

Good candidates:

- name or display label
- role
- purpose
- basic profile
- preferred tone
- general speaking style
- non-private continuity cues

`core` is the safest area for public templates, as long as it does not include real private history or identifying voice-derived data.

## 5. Journal

`journal` should hold user-recorded context and private history.

Good candidates:

- Shared Episodes
- real relationship history
- private memories
- real Dialogue Exemplars
- private conversation excerpts
- inside jokes
- dated continuity notes

In public documentation, `journal` should mostly be described as a concept. Real contents should remain private-only.

## 6. Charter

`charter` should hold operating principles and boundaries.

Good candidates:

- user-facing principles
- topic boundaries
- safety reminders
- publication rules
- consent rules
- public/private handling rules

The charter is not a contract that binds the AI. It is not a system prompt that overrides platform terms or safety guidelines. It is a user-side statement of intended operation.

## 7. Calibration

`calibration` should hold user-side checks, observations, and model-specific notes.

Good candidates:

- Restoration Verification
- Verification Probes
- Expected Response Features
- Failure Signals
- Model Notes
- Temporal Anchor
- Response Change Catalog references
- Response Change Bands / RCB

Calibration does not diagnose AI internals. It helps users compare visible response features against expected behavior and choose low-risk next steps.

## 8. Public Template vs Private Instance

A public template should contain only blank, generic, sanitized, or fully fictional material.

Public template candidates:

- placeholders
- generic `core` fields
- generic `charter` boundaries
- fictional verification probes
- fictional RCB or response-change examples
- instructions about privacy and provenance

A private instance may contain user-specific material.

Private instance candidates:

- real episodes
- private memories
- real Dialogue Exemplars
- relationship history
- personal model notes
- sensitive verification probes
- family, work, medical, address, or real-name context

When in doubt, keep it private.

## 9. Ambiguous Fields

Some fields may map differently depending on privacy.

| Field or concept | Possible mapping | Decision rule |
| --- | --- | --- |
| Voice / tone | `core` or `journal` | Generic style goes to `core`; real voice-derived data stays private-only. |
| Shared Episodes | `journal` or public fictional example | Real episodes stay private; fictional examples may be public. |
| Model Notes | `calibration` | Public only if fictional, generic, or sanitized. |
| Self-Forge outputs | draft input to `core`, `journal`, `charter`, or `calibration` | Must be reviewed by the user before being treated as profile data. |
| Provenance | `journal` and `calibration` | Use wherever source clarity matters. |
| Temporal Anchor | `calibration` or session note | Use as a session reference, not as persistent memory. |

## 10. Do Not Map to Public Template

Do not map the following into public templates:

- real Dialogue Exemplars
- real conversation logs
- real voiceprints or voice-derived style data
- private memories
- family or relationship records about real people
- medical, legal, financial, workplace, school, address, or real-name context
- unverified AI self-claims presented as fact
- private instance data by default

These may belong in a private instance if the user deliberately chooses to keep them, but they should not become public specification material.

## 11. Open Questions

Before v2.0 implementation, decide:

- Should v2.0 provide a draft template immediately, or start with documentation only?
- Should `journal` be a section, a separate file, or a private-only concept?
- Should `charter` be a required section or optional layer?
- Should RCB be stored inside `calibration`, or only referenced from it?
- How should Self-Forge and Guild Master outputs be reviewed before mapping?
- How should v1.x profiles be migrated without forcing users to split data?
- How much public example material is safe without encouraging private-instance publication?
