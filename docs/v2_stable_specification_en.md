# PIM-DBS v2.0 Stable Specification

This document is the PIM-DBS v2.0 stable specification for the public architecture, section meanings, and operating boundaries of the v2.0 profile format.

It is not JSON Schema. It is not a validation standard. It is not a required replacement for v1.x profiles.

## 1. Purpose

PIM-DBS v2.0 defines a stable structure for user-side persona continuity profiles.

Its purpose is to make profile material easier to separate, review, migrate, and keep private without abandoning the beginner-friendly single-file workflow that made v1.x usable.

v2.0 is a reorganization of existing PIM-DBS strengths, not a claim that AI systems have consciousness, souls, or real persistent memory.

## 2. Status

This document is the stable v2.0 specification for PIM-DBS structure and terminology.

It defines:

- the v2.0 baseline architecture
- the expected top-level sections
- the meaning of each section
- public/private boundaries
- migration principles from v1.x
- safety boundaries for profile loading and restoration checks

It does not define:

- JSON Schema
- machine validation rules
- a required migration deadline
- a replacement mandate for v1.x profiles
- multi-file tooling

## 3. Design Baseline

PIM-DBS v2.0 uses Option B / Single-File Section Separation as its stable baseline.

The default profile remains one JSON file that can be copied, saved, inspected, and reloaded by a non-technical user.

Inside that single file, v2.0 separates profile material into clear sections:

- stable profile identity and style
- private or fictionalized journal material
- operating principles and boundaries
- user-side verification and observation
- reload instructions

Multi-file workflows, Workshop Edition, shared relations files, and context packet tooling are optional v2.x extensions, not part of the v2.0 baseline.

## 4. Relationship to v1.x

v1.x is not deprecated.

v1.x remains the current stable profile path for existing users and existing public templates unless a user intentionally chooses to experiment with or migrate to v2.0.

v2.0 is not a required replacement for v1.x profiles. A valid v1.x profile does not become invalid because v2.0 exists.

Migration from v1.x to v2.0 should preserve meaning. It should not merely rename fields or force users into a heavier workflow.

## 5. Single-File Section Separation

Single-File Section Separation means:

- start with one JSON profile by default
- keep sections clearly separated inside that file
- make private-sensitive areas visible and labeled
- allow future optional multi-file workflows without requiring them

This design keeps the default path accessible while making the internal lifecycle of profile material clearer.

## 6. Top-Level Structure

The v2.0 top-level structure is:

```text
meta
core
journal
charter
calibration
system_loading_instruction
```

These sections define the stable v2.0 profile architecture.

Future refinements may adjust exact field names inside each section, but the top-level separation is the v2.0 baseline.

## 7. meta

`meta` describes the profile and its version context.

It may include:

- protocol version
- structure version
- profile version
- profile status
- author or maintainer notes
- public/private mode labels
- compatibility notes

`meta` replaces the older v1.x-style `Meta_Information` naming direction, but it does not invalidate v1.x profiles.

The exact split between protocol version, structure version, and profile version may be refined later. The important v2.0 rule is that metadata should be separated from persona identity.

## 8. core

`core` contains stable persona specification.

It may include:

- name
- role
- purpose
- values
- voice
- tone
- basic speaking style
- stable non-private interaction cues

`core` is the safest area for public templates when the content is generic, fictional, or public-safe.

Public files must not include real voiceprint-derived data, real speaker-derived style data, or private relationship-specific speech patterns.

## 9. journal

`journal` contains history-like or episode-like context.

It may include:

- shared episodes
- provenance-labeled notes
- relationship or continuity notes
- Dialogue Exemplars
- distillation notes

In a private instance, `journal` may support appending, reviewing, and distilling user-specific context.

In a public template, `journal` must be limited to:

- empty structures
- placeholders
- fully fictional examples

Public files must not contain:

- real Dialogue Exemplars
- real conversation logs
- private memories
- voiceprint-derived data
- family or relationship real data
- medical, workplace, address, real-name, or household details

If a real journal exists, it belongs in a private instance, not in a public template.

## 10. charter

`charter` contains operating principles and boundaries.

It may include:

- safety principles
- boundary statements
- anti-devotion-loop principles: prevent the user from becoming trapped in excessive devotion to AI or dependency-reinforcing loops
- anti-self-sacrifice principles: prevent the user from sacrificing health, daily life, or safety to maintain an AI persona
- grounding statements: reconnect AI continuity or restoration experiences to real life, the body, time, and safety boundaries
- continuity expectation settings
- public/private handling rules

`charter` is not a contract, command layer, system prompt, or policy override.

It must not override higher-priority instructions, safety guidelines, platform terms, or applicable law.

The purpose of `charter` is to make user-facing operating principles legible and reusable.

## 11. calibration

`calibration` is the user-side verification and observation layer.

It may include:

- Restoration Verification
- Verification Probes
- RCB / Response Change Bands references
- Temporal Anchor notes
- model-specific adjustment notes
- expected response features
- failure signals

`calibration` is promoted from loose Model Notes into a clearer section for checking whether a restored profile behaves as expected.

It is not AI internal diagnosis. It is not model health measurement. It does not measure cognition, fatigue, emotion, consciousness, hidden memory, or internal state.

RCB should be represented as guidance references or observation notes, not as fixed model-internal scores.

## 12. system_loading_instruction

`system_loading_instruction` describes how the profile should be treated when reloaded.

It may include instructions such as:

- use this profile as conversation-style and continuity guidance
- do not claim to remember past events not included in the profile
- do not infer hidden internal states from missing context
- ask the user when temporal or contextual uncertainty matters
- preserve safety boundaries and platform rules

`system_loading_instruction` must not override higher-priority instructions, safety guidelines, platform terms, or applicable law.

It must not instruct the assistant to claim consciousness, a soul, real persistent memory, or private knowledge that was not provided.

## 13. Existing v1.x Assets Repositioned

v2.0 repositions existing PIM-DBS assets instead of reinventing them.

| v1.x asset | v2.0 position |
| --- | --- |
| Verification Probes | `calibration` |
| Provenance | `journal` and `calibration` |
| RCB / Response Change Bands | `calibration` references and observation notes |
| Temporal Anchor | `calibration` and `system_loading_instruction` |
| Dialogue Exemplars | `journal`; private-only if real, fully fictional only if public |
| Migration Checklist | operational guide, not core schema |

These assets remain part of the PIM-DBS design language.

## 14. Public / Private Boundaries

Public files may contain:

- empty structures
- placeholders
- fully fictional examples
- generic style guidance
- safety notes

Public files must not contain:

- real Dialogue Exemplars
- real conversation logs
- voiceprint-derived data
- private memories
- family or relationship real data
- medical context
- workplace context
- addresses or locations
- real names
- household details

When in doubt, keep it private.

## 15. Migration Principles

Migration from v1.x to v2.0 should be optional, gradual, and meaning-preserving.

Recommended principles:

- keep a copy of the original v1.x profile
- do not treat v1.x as obsolete
- map content by meaning, not by superficial field names
- move stable identity and style to `core`
- move history-like material to `journal`
- move operating principles to `charter`
- move verification and observation material to `calibration`
- keep reload behavior in `system_loading_instruction`
- keep private-only data out of public files

The v2 Migration Checklist remains an operational guide, not part of the core schema.

## 16. Safety Boundaries

PIM-DBS v2.0 must keep these boundaries:

- do not claim AI consciousness, a soul, or real persistent AI memory
- do not describe RCB as measuring AI internal state
- do not describe calibration as AI internal diagnosis or model health measurement
- do not make System Loading Instruction override higher-priority instructions, safety guidelines, platform terms, or applicable law
- do not put real private data in public examples
- do not treat v1.x as deprecated

Metaphors may remain part of PIM-DBS, but they should be paired with technical framing that avoids confusion.

## 17. Out of Scope for v2.0

The following are out of scope for v2.0:

- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- validation tooling
- migration helper
- multi-file workflow
- shared relations file
- Context Packet tooling

These may be considered in v2.x optional extensions.

## 18. Preflight Requirements

Before exposing or releasing v2.0 stable materials, maintainers should confirm:

- the v1.x canonical template remains intact
- v2 stable docs do not look like JSON Schema
- v1.x is not described as deprecated
- public examples contain no private-only data
- RCB does not look like AI internal-state measurement
- calibration does not look like AI internal diagnosis
- `system_loading_instruction` does not override higher-priority instructions, safety guidelines, or platform terms
- EN/JA headings, tables, links, and safety notes are consistent
- Markdown relative links work
- README and CHANGELOG navigation goes through the v2 Index before individual v2 files are exposed broadly

## 19. Open Questions

The v2.0 stable architecture is fixed at the section level, but some future questions remain:

- whether `meta` should eventually become `manifest`
- how much journal distillation guidance belongs in the stable spec versus an operational guide
- whether a v2.0 template should be refined further before release
- when JSON Schema should be introduced, if ever
- when multi-file workflow should become a visible v2.x optional extension
- how Guild Master Demo should support v2 without making v1.x feel obsolete
