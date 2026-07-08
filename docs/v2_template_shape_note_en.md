# PIM-DBS v2.0 Template Shape Note

This document is a non-normative design note. It explores the possible shape of a future PIM-DBS v2.0 draft template before any template file is created.

It is not a v2.0 draft template, JSON Schema, `probes.json`, `packet.md`, or implementation plan. It does not invalidate v1.x single-JSON templates.

## 1. Purpose

The purpose of this note is to decide what shape a future v2.0 draft template should probably take if PIM-DBS adopts the candidate structure:

- `core`
- `journal`
- `charter`
- `calibration`

The goal is to reduce design risk before creating any actual v2.0 template.

## 2. Recommended Starting Shape

The recommended starting point is a single JSON draft template.

Reasons:

- It keeps migration from v1.x easier.
- It avoids introducing a multi-file workflow too early.
- It is easier for beginners to copy, save, and reload.
- It lets the project test the v2.0 structure before committing to file splitting.

Multiple files may be useful later, but they should probably wait until the v2.0 structure is stable.

## 3. Candidate Top-level Sections

A possible top-level shape is:

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

These names are design candidates, not final schema keys.

## 4. Single JSON vs Multiple Files

For the first v2.0 draft template, a single JSON file is safer.

Single JSON advantages:

- familiar to v1.x users
- easier to publish as a public template
- easier to inspect manually
- lower risk of losing private sections during early use

Multiple-file advantages:

- stronger separation of public and private material
- easier private-only handling for `journal`
- future compatibility with `packet.md`, migration helpers, or tooling

Recommendation: start with one JSON draft, then consider optional file separation in v2.1 or later.

## 5. Core

`core` should be a top-level section.

It should contain stable, reusable profile information:

- identity
- role
- purpose
- tone
- general speaking style
- non-private continuity cues

`core` is the safest section for public templates and fictional examples. It should not contain real private history or real voiceprint-derived data.

## 6. Journal

`journal` should be a top-level section, but public templates should treat it carefully.

Possible public template options:

- empty structure
- placeholders
- clearly fictional example episode
- private-only note

Recommendation: public templates should use an empty structure or a clearly fictional single example. Real journal contents should remain private instance data.

Do not place real Dialogue Exemplars, real conversation logs, private memories, real relationship history, family relations, or voice-derived data in public `journal` examples.

## 7. Charter

`charter` should probably be a lightweight required section in v2.0 draft templates.

Reason:

- it keeps safety boundaries visible
- it clarifies public/private handling
- it explains operating principles without turning them into commands

The charter is not a contract, command layer, system prompt, or override of safety guidelines and platform terms. It is a user-side statement of operating principles and boundaries.

## 8. Calibration

`calibration` should probably be optional but recommended.

Reason:

- some users may only need a simple profile
- advanced users benefit from Restoration Verification, Model Notes, Temporal Anchor usage, and RCB references
- it keeps verification and observation separate from persona identity

Calibration is not AI internal diagnosis. It is a user-side layer for checking visible response features and choosing low-risk next steps.

## 9. RCB Placement

RCB should not be stored as a permanent score in the template.

Recommended placement:

- `calibration.response_change_bands.reference`
- `calibration.response_change_bands.observation_notes`
- `calibration.response_change_bands.user_side_responses`

Avoid:

- storing a fixed RCB number
- treating RCB as model health
- asking the AI to self-report RCB
- presenting RCB as a measurement of internal state

RCB should remain a guide-linked observation method for visible response changes.

## 10. Meta Information

`Meta_Information` from v1.x should probably become a top-level `meta` section.

Reason:

- protocol version, profile version, author, target model, and privacy status are not persona identity
- separating `meta` keeps `core` focused on the persona profile
- future migration can distinguish protocol version, schema/draft version, and user profile version

Open question: whether v2.0 should use `meta` immediately, or keep `Meta_Information` during the first draft for v1.x familiarity.

## 11. Cognitive Framework / TCF

The v1.x `Cognitive_Framework` and TCF-related concepts need careful handling.

Possible placements:

- keep a `cognitive_framework` section as a descriptive profile area
- map values and interaction principles into `charter`
- map observable response checks into `calibration`
- keep style and routine preferences in `core`

Recommendation: do not scatter TCF across too many sections too early. A lightweight `cognitive_framework` subsection inside `core`, or a clearly labeled descriptive section, may be safer for the first draft.

TCF should not be described as AI internal cognition. It should describe user-requested interaction patterns, response preferences, and operational framing.

## 12. System Loading Instruction

`system_loading_instruction` should be its own top-level section.

Reason:

- it is operationally important
- it should be easy to copy at reload time
- it needs strong safety wording

It should state:

- this is user-provided context
- it describes desired conversation style and boundaries
- it does not override safety guidelines, platform terms, or higher-priority instructions
- the assistant should not claim memories or internal states not provided in the profile
- uncertain time context should be confirmed with the user

## 13. Family Network and Inside Jokes

`Family_Network` and `Inside_Jokes` should be treated as high-risk public-template material.

For public templates:

- use empty placeholders
- use clearly fictional examples only
- include private-only warnings
- avoid real family roles, real relationship maps, private jokes, or identifying context

For private instances:

- users may keep this material locally if they understand the privacy risk
- provenance and privacy notes should be clear

Recommendation: do not include realistic family or inside-joke examples in public v2.0 templates.

## 14. v1.x Compatibility

v2.0 should not invalidate v1.x single-JSON templates.

Compatibility guidance should say:

- v1.x profiles remain usable
- v2.0 is a clearer structure, not a mandatory replacement
- users do not need to split existing profiles immediately
- v1.x fields can be mapped gradually into `meta`, `core`, `journal`, `charter`, and `calibration`
- beginner users can keep using simpler formats

The first v2.0 draft should be easy to compare with the v1.x template.

## 15. Avoiding Schema-like Overcommitment

The v2.0 draft template should avoid looking like a final schema too early.

Recommended safeguards:

- label it as a draft
- include a non-normative note
- avoid strict validation language
- avoid JSON Schema keywords unless a schema is intentionally created
- avoid claiming the structure is final
- avoid adding too many nested fields in the first draft

The draft should invite review, not imply that v2.0 is already locked.

## 16. Open Questions

Before creating the v2.0 draft template, decide:

- Should the first draft use `meta` or keep `Meta_Information`?
- Should `charter` be required or recommended?
- Should `calibration` be optional or recommended?
- Should `cognitive_framework` remain as a named section?
- Should `journal` include one fictional example or only placeholders?
- Should `Dialogue_Exemplars` live only under `journal`?
- Should `Inside_Jokes` be excluded from public templates by default?
- Should `Family_Network` be renamed, minimized, or private-only?
- Should RCB be represented as references only?
- How much v1.x naming should remain for migration comfort?

## 17. Provisional Shape Summary

Provisional recommendation:

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

Status by section:

| Section | Recommended status | Notes |
| --- | --- | --- |
| `meta` | required candidate | Separate from persona identity. |
| `core` | required candidate | Stable public-safe profile material. |
| `journal` | optional / private-sensitive | Public template should use empty or fictional content only. |
| `charter` | lightweight required candidate | Operating principles and boundaries. |
| `calibration` | optional but recommended | User-side verification and observation. |
| `system_loading_instruction` | required candidate | Must include safety and platform-term limits. |
