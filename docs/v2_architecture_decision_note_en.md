# PIM-DBS v2.0 Architecture Decision Note

This document is a non-normative architecture decision note. It is a design input for stabilizing a future PIM-DBS v2.0 specification, not the stable v2.0 specification itself.

It does not replace v1.x profiles, define a final schema, create a validation standard, or require users to move away from the current v1.x stable profile path.

## 1. Purpose

The purpose of this note is to evaluate the central v2.0 design tension:

- the power of structural separation
- the kindness of a single file that a non-technical user can start with

PIM-DBS v2.0 should improve separation without making the default workflow too heavy for users who need a simple, readable, copyable profile.

## 2. Background

The v2 Draft / Preview materials have already explored:

- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

They also introduced a non-normative single-JSON v2 draft template and operational support materials. The next design step is to decide whether v2.0 stable should default to a multi-file architecture or keep the first experience as a single-file profile with clearer internal sections.

## 3. What v1.x Already Provides

v1.x already contains several important user-side mechanisms:

- Verification Probes
- Provenance
- RCB / Response Change Bands
- Temporal Anchor
- Dialogue Exemplars
- Migration Checklist

v2.0 should not reinvent these mechanisms. It should reposition them inside a clearer architecture.

In other words, v2.0 should reorganize existing strengths instead of treating them as failed or obsolete.

## 4. Core Design Tension

Multi-file separation is powerful.

It can make boundaries clearer, reduce accidental publication of private material, and support future tooling such as context packets, migration helpers, or validators.

However, the default PIM-DBS flow must remain something a non-technical user can begin with in one file.

The project should not lose the original kindness of PIM-DBS: a person should be able to preserve a usable profile without understanding repository layouts, schemas, or file orchestration.

## 5. Option A: Two-Edition Model

Option A would define two editions:

- Single-File Edition
- Workshop Edition

Single-File Edition would be the beginner-friendly default. Workshop Edition would allow multi-file organization for advanced users, maintainers, or teams.

Benefits:

- clear naming for different user levels
- room for future multi-file workflows
- easier explanation of public/private boundaries for advanced use

Risks:

- users may think one edition is more "real" than the other
- documentation may become heavier
- v2.0 may look like a product split instead of a profile format

Option A is attractive, but it may be better as a v2.x expansion after the stable v2 structure is settled.

## 6. Option B: Single-File Section Separation

Option B keeps v2.0 stable as a single JSON profile by default, while separating the structure internally:

- `meta`
- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

External journal files, shared relation files, context packets, or workshop workflows would remain optional extensions.

Benefits:

- preserves the v1.x single-file kindness
- keeps the first migration path simple
- avoids making v2.0 look like a tooling platform too early
- still gives enough structure for public/private separation

Risks:

- private material may still be placed inside one file if users ignore guidance
- optional extensions may be delayed
- advanced users may want stronger file boundaries sooner

Option B fits the current v2 Draft / Preview direction.

## 7. Recommended Direction

The recommended direction is to evaluate Option B as the v2.0 stable baseline.

That means:

- v2.0 starts as a single-file profile with strong internal section separation
- v1.x remains valid and is not deprecated
- multi-file workflow remains optional and deferred
- Workshop Edition, shared relations files, and context packet tooling can be explored in v2.x

This note does not make the final decision. It records the current architectural preference before a stable v2.0 specification is written.

## 8. Required v2.0 Components

The following components appear necessary for v2.0 stable:

- manifest or `meta` version clarification
- lifecycle separation for `core`, `journal`, `charter`, and `calibration`
- independent `charter` framing
- journal append and distill guidance
- calibration promoted from loose Model Notes into a user-side verification and observation layer
- v1.x migration that preserves meaning instead of merely renaming fields
- explicit public/private boundaries

These components should remain understandable inside a single-file default profile.

## 9. Optional / Deferred Components

The following should remain optional or deferred:

- multi-file workflow
- shared relations file
- Context Packet tooling
- Guild Master Demo v2 support
- JSON Schema
- `probes.json`
- `packet.md`
- validation tooling
- migration helper

These may be valuable later, but including them in the first stable v2.0 scope could make the system feel heavier than necessary.

## 10. What v2.0 Must Not Redesign

v2.0 should not redesign these existing assets from scratch:

- RCB / Response Change Bands
- Provenance
- Verification Probes
- Dialogue Exemplars
- Temporal Anchor

They should be repositioned inside the v2.0 architecture, not renamed into unrelated systems or treated as discarded v1.x ideas.

## 11. Open Questions

- Should v2.0 stable name the default format "Single-File Edition", or should it avoid edition language until v2.x?
- How much journal distillation guidance belongs in the stable spec versus a separate operational guide?
- Should `meta` use a manifest-like shape, or stay as a lightweight metadata section?
- How should public examples show `journal` without encouraging users to publish private history?
- When should Workshop / multi-file support become visible in README-level documentation?

## Safety Boundaries

- v1.x must not be treated as deprecated.
- v2.0 must not be presented as a required replacement for v1.x profiles.
- The default flow should not become complex.
- Real Dialogue Exemplars, real conversation logs, voiceprint-derived data, private memories, and real family or relationship data must not be placed in public examples.
- PIM-DBS does not claim AI consciousness, a soul, or real persistent memory.
- RCB must not be described as a measurement of AI internal state.
- Calibration must not be described as AI internal diagnosis.
- `system_loading_instruction` must not override higher-priority instructions, safety guidelines, or platform terms.
