# PIM-DBS v2.0 Stabilization Note

This document is a non-normative stabilization note for preparing a future PIM-DBS v2.0 stable specification.

It is not a JSON Schema, not a validation standard, not a release note, and not the final v2.0 specification. It records the stabilization direction before the stable specification is written.

## 1. Purpose

The purpose of this note is to stabilize the architectural direction for PIM-DBS v2.0 before writing the stable specification.

It follows the Architecture Decision Note and turns the evaluated direction into a working stabilization decision.

## 2. Background

By v1.9.0, the project has prepared:

- v2 Draft / Preview materials
- v2 draft template
- Migration Checklist
- Preflight Guide
- Fictional Migration Example
- Architecture Decision Note
- v2 Index navigation

These materials are enough to choose a stable direction without turning v2.0 into a heavy tooling system too early.

## 3. Stabilization Decision

PIM-DBS v2.0 adopts Option B / Single-File Section Separation as the baseline for the stable specification.

This means:

- the default profile starts as one JSON file
- the file is internally separated into clear sections
- multi-file workflows are optional extensions, not the default path
- v1.x profiles remain valid and are not deprecated

The decision prioritizes a beginner-friendly default while still improving public/private separation and lifecycle clarity.

## 4. Confirmed v2.0 Direction

The confirmed v2.0 direction is:

- keep the default flow startable from one JSON file
- use clear top-level structural areas
- reposition existing v1.x assets instead of reinventing them
- make public/private boundaries more explicit
- keep optional complexity out of the stable baseline

The expected stable direction remains compatible with the current draft shape:

- `meta`
- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

These names may still be refined, but the structural direction is now stable enough to guide the v2.0 specification work.

## 5. v2.0 Stable Scope

The v2.0 stable scope should include:

- version clarification through `meta` or a manifest-like section
- structural separation of `core`, `journal`, `charter`, `calibration`, and `system_loading_instruction`
- independent framing for `charter`
- journal append and distill guidance
- promotion of calibration from loose Model Notes into a user-side verification and observation layer
- explicit public/private boundaries
- v1.x migration that preserves meaning

The stable scope should not require users to adopt multi-file workflows.

## 6. Required Components

The following components are required for v2.0 stabilization:

- a clear draft-to-stable version story
- a stable explanation of each top-level area
- guidance for what belongs in public templates
- guidance for what remains private-only
- migration language that does not invalidate v1.x
- safety language for System Loading Instruction
- calibration language that avoids AI internal diagnosis
- RCB language that avoids internal-state measurement

These requirements should be met in the stable specification before any release labeled v2.0 stable.

## 7. Existing v1.x Assets to Reposition

The following v1.x assets should be repositioned inside the v2.0 architecture:

- Verification Probes
- Provenance
- RCB / Response Change Bands
- Temporal Anchor
- Dialogue Exemplars
- Migration Checklist

They should not be redesigned from scratch.

Their role should become clearer inside `core`, `journal`, `charter`, `calibration`, or supporting guidance, depending on the asset.

## 8. Optional / Deferred Components

The following components should remain optional or deferred:

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- validation tooling
- migration helper
- multi-file workflow
- shared relations file
- Context Packet tooling

These may become valuable in v2.x, but they should not block the first stable v2.0 specification.

## 9. Relationship to v1.x

v2.0 does not invalidate v1.x.

v1.x remains the current stable profile path until a stable v2.0 specification is released, and even then v1.x profiles should remain understandable and migratable.

The goal of v2.0 is not to punish existing profiles. It is to provide a clearer structure for users who need stronger separation.

## 10. Public / Private Boundaries

v2.0 stable must preserve a strong boundary between public templates and private instances.

Public templates may include:

- generic profile structure
- fully fictional examples
- public-safe placeholders
- non-private tone and role descriptions

Public templates must not include:

- real Dialogue Exemplars
- real conversation logs
- voiceprint-derived data
- private memories
- real family or relationship data
- medical, workplace, address, real-name, or household context

`journal` should be especially careful: public files should use an empty structure, placeholders, or fully fictional examples only.

## 11. Safety Boundaries

PIM-DBS v2.0 must keep these safety boundaries:

- do not claim AI consciousness, a soul, or real persistent AI memory
- do not describe RCB as measuring AI internal state
- do not describe calibration as AI internal diagnosis or model health measurement
- do not make System Loading Instruction override higher-priority instructions, safety guidelines, or platform terms
- do not place real private data in public examples
- do not treat v1.x as deprecated

The metaphors of PIM-DBS may remain, but they should be paired with clear technical framing.

## 12. Preflight Conditions Before v2.0 Release

Before any v2.0 stable release, maintainers should confirm:

- v1.x canonical template remains available
- v2.0 stable wording does not call v1.x deprecated
- public examples contain only fictional or placeholder content
- v2.0 stable scope does not include JSON Schema unless deliberately added later
- all EN/JA links and headings are consistent
- the stable spec does not claim AI consciousness, soul, or real memory
- RCB and calibration remain user-side observation and verification layers
- System Loading Instruction safety boundaries remain explicit

## 13. Open Questions

- Should the stable v2.0 document use `meta` or `manifest` terminology?
- Should `journal` distillation guidance live inside the stable spec or in an operational guide?
- How much of the v2 draft template should be promoted directly into the stable spec?
- Should the v2.0 release include a migration example as official supporting material?
- When should multi-file workflow become visible as a v2.x optional extension?
