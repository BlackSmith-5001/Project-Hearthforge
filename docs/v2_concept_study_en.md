# PIM-DBS v2.0 Concept Study

This document is a concept study for PIM-DBS v2.0. It organizes possible structural changes before implementation.

This is a non-normative concept study. It is an exploration for future v2.0 design, not a committed v2.0 specification.

v2.0 is not meant to invalidate v1.x usage. The v1.x single JSON profile remains a valid and practical format. v2.0 explores how the same ideas could be separated more clearly for public templates, private instances, restoration checks, and long-term maintenance.

## 1. What v2.0 Is For

PIM-DBS v2.0 is for structural separation.

The main goal is to separate:

- stable persona profile data
- private history and user-recorded context
- operating principles and boundaries
- verification, observation, and model-specific notes

This should make PIM-DBS easier to maintain, safer to publish, and easier to adapt across different AI systems without claiming persistent AI memory, consciousness, emotions, or a soul.

## 2. What v2.0 Is Not

v2.0 is not:

- a claim that AI has persistent internal memory
- a claim that PIM-DBS stores consciousness, emotions, or a soul
- a mechanism for overriding safety guidelines or platform terms
- a reason to publish private instances
- a replacement for v1.x profiles
- a full schema, toolchain, or automation layer by itself

Metaphors such as ark, forge, soul, or summoning may remain as project language, but public technical wording should pair them with user-side context profile, restoration guide, verification layer, or operational boundary.

## 3. Proposed Structure

The proposed v2.0 structure separates the profile into four conceptual areas.

### core

`core` contains the stable public-facing profile elements.

Possible contents:

- name or display label
- role
- purpose
- preferred tone
- communication style
- safety notes
- non-private continuity cues

`core` is the safest candidate for public templates and fictional examples.

### journal

`journal` contains private user-recorded context.

Possible contents:

- Shared Episodes
- private conversation history
- dated notes
- user-recorded continuity context
- real Dialogue Exemplars
- emotionally significant events

In public documentation, `journal` should be treated as a structural concept. Real contents should remain in private instances unless deliberately sanitized.

### charter

`charter` contains operating principles and boundaries.

Possible contents:

- preferred interaction principles
- boundaries for topics or style
- safety reminders
- public/private handling rules
- consent and publication rules

The charter is not a contract that binds the AI, and it is not a system instruction that overrides platform rules. It is a user-side statement of intended operation and boundaries.

### calibration

`calibration` contains user-side checks and model-specific notes.

Possible contents:

- Restoration Verification
- Verification Probes
- Expected Response Features
- Failure Signals
- Response Change Bands (RCB)
- Response Change Catalog references
- Model Notes
- last verification date

Calibration does not diagnose AI internals. It helps the user check whether the reconstructed response style and operating context are close enough for the current session.

## 4. Public Template vs Private Instance

v2.0 should make the boundary between public templates and private instances more explicit.

A public template may include:

- blank structures
- fictional examples
- placeholder fields
- generic safety notes
- example probes that do not reveal real people or private events

A private instance may include:

- real user context
- real conversation history
- private episodes
- model-specific observations from private use
- non-public Dialogue Exemplars
- sensitive relationship or identity context

When in doubt, keep it private.

## 5. Dialogue Exemplars and Private-only Data

Dialogue Exemplars are useful for reconstructing response style, but they can expose private tone, relationship patterns, inside jokes, and real conversation history.

For v2.0, the recommended public stance is:

- fictional Dialogue Exemplars may be used in public examples
- real Dialogue Exemplars should be private-only
- real voiceprints, private chat logs, and identifying speech patterns should not become public specification material
- provenance should remain explicit where examples or episodes are recorded

Public examples should use fully fictional personas only.

## 6. Dual Backup Redesign

The original Dual Backup System idea can be clarified in v2.0 as a separation between two forms of continuity support.

Possible framing:

- `core backup`: stable profile, role, style, purpose, boundaries
- `context backup`: private journal, episodes, exemplars, verification notes, model notes

A possible mapping is: core backup = core + charter, and context backup = journal + calibration.

This keeps the philosophical idea of preserving continuity while reducing the risk that a public template is mistaken for a private memory archive.

The redesign should not claim that AI memory is being backed up. It should describe a user-side backup of profile context and restoration instructions.

## 7. Migration From v1.x

v2.0 should preserve the v1.x user path.

Important migration principles:

- v1.x single JSON profiles remain valid
- v2.0 should not require existing users to split their data immediately
- v1.x fields should map naturally into the new conceptual areas
- Markdown profiles should remain beginner-friendly simplified formats
- Self-Forge and Guild Master should remain profile creation aids, not sources of verified facts

Possible mapping:

| v1.x area | v2.0 conceptual area |
| --- | --- |
| Core Identity | core |
| Contextual Profile | core or journal, depending on privacy |
| Shared Episodes | journal |
| Dialogue Exemplars | journal, private-only if real |
| Restoration Verification | calibration |
| Model Notes | calibration |
| System Loading Instruction | charter and core |

## 8. Deferred Items

The following items are better candidates for v2.1 or later:

- JSON Schema
- `probes.json`
- Guild Master Demo v2 mode
- `packet.md` generation workflow
- migration helper
- expanded fictional examples
- validation tooling
- formal import/export utilities

These are valuable, but adding them directly to v2.0 may make the first structural release too large.

## 9. Safety Boundaries

v2.0 should keep the following boundaries explicit:

- PIM-DBS does not store AI consciousness, emotions, a soul, or persistent hidden memory.
- PIM-DBS profiles describe user-side context, preferred style, restoration instructions, and verification cues.
- Private instances should not be published by default.
- Real Dialogue Exemplars, real voiceprints, real chat logs, family relations, medical context, workplace details, addresses, real names, and private relationship context should remain private.
- RCB and Restoration Verification are user-side checks of visible output, not diagnoses of AI internal state.
- PIM-DBS does not override safety guidelines, platform terms, or system-level instructions.

## 10. Open Questions

Before implementation, the following questions should be answered:

- Should v2.0 provide a draft JSON template, or only documentation first?
- Should `journal` be represented as a file, a section, or only a private concept?
- Should `charter` be a lightweight section or a separate document?
- Should `calibration` include RCB directly, or only link to RCB guidance?
- Should `packet.md` be introduced as a manual export example or deferred entirely?
- How much migration guidance is enough for v1.x users?
- Should Guild Master produce v1.x profiles until v2.0 is stable?
- What should be the minimum public example for v2.0 without exposing private-style data?

## Classification Summary

| Candidate | Classification | Notes |
| --- | --- | --- |
| core / journal / charter / calibration separation | v2.0 core | Conceptual separation only at first. |
| public template / private instance boundary | v2.0 core | Must be explicit. |
| Dialogue Exemplars private-only policy | v2.0 core | Public examples should stay fictional. |
| real voiceprints, real conversations, private records non-public policy | v2.0 core | Safety boundary. |
| Dual Backup redesign | v2.0 core | Reframe as profile/context backup, not AI memory backup. |
| v1.x migration path | v2.0 core | Preserve existing users. |
| lightweight Charter structure | v2.0 optional | Useful if kept small. |
| optional `packet.md` example | v2.0 optional | Should not become required. |
| RCB / Response Change Catalog connection | v2.0 optional | Link calibration to existing guidance. |
| JSON Schema | v2.1 or later | Too heavy for first structural release. |
| `probes.json` | v2.1 or later | Better after calibration shape is stable. |
| Guild Master Demo v2 support | v2.1 or later | Avoid coupling demo to unstable structure. |
| `packet.md` generation workflow | v2.1 or later | Needs design first. |
| migration helper | v2.1 or later | Useful after final mapping exists. |
| real Dialogue Exemplars | private-only | Do not publish. |
| real conversation logs | private-only | Do not publish. |
| real voiceprint or tone-source data | private-only | Do not publish or make a public spec. |
| family / relations real data | private-only | Do not publicize. |
| public real voiceprint specification | do not include | High misuse and privacy risk. |
| AI soul, consciousness, or real-memory claims | do not include | Outside safe project framing. |
| AI internal-state self-reporting | do not include | Conflicts with RCB safety framing. |
