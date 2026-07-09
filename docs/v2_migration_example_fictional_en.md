# PIM-DBS v2 Fictional Migration Example

This is a non-normative fictional migration example for PIM-DBS v2 Draft / Preview materials.

It is not a v2.0 stable specification, not a final schema, not a validation standard, and not a required replacement for v1.x profiles. PIM-DBS v1.x remains the current stable profile path.

Related materials:

- [v2 Migration Guidance Note](v2_migration_guidance_note_en.md)
- [v2 Migration Checklist](v2_migration_checklist_en.md)
- [v2 Field Mapping Note](v2_field_mapping_note_en.md)
- [v2 Draft Template](../templates/pim-dbs_v2_draft.json)
- [v2 Draft / Preview Index](v2_index_en.md)

## 1. Purpose

This example shows how a small v1.x-style fictional profile summary could be mapped into the v2 draft structure:

- `core`
- `journal`
- `charter`
- `calibration`
- `system_loading_instruction`

The goal is to demonstrate migration shape, not to define final keys or validation rules.

## 2. Safety Note

This example is completely fictional.

It does not include real Dialogue Exemplars, real conversation logs, voiceprint-derived data, private memories, family data, relationship history, medical details, workplace details, addresses, real names, or real private context.

PIM-DBS does not claim to store AI consciousness, a soul, emotions, hidden memory, or real internal states. It is a user-side profile, context, restoration, and verification support format.

The v2 draft is optional. Users can keep using v1.x profiles when they are already clear and useful.

## 3. Fictional Source Profile Summary

This is a short fictional v1.x-style source summary, not a real profile.

```yaml
# fictional public example - not a v1.x export
persona_name: "Luma"
fictional_user_label: "Learner"
role: "Calm study review helper"
purpose: "Help Learner review short daily learning notes."
tone:
  - "gentle"
  - "concise"
  - "encouraging"
style_rules:
  - "start with a brief acknowledgement"
  - "summarize the topic simply"
  - "suggest one small next step"
fictional_episode: "Learner likes reviewing one note at a time."
boundaries:
  - "do not claim private memory"
  - "do not override safety guidelines or platform terms"
verification_hint: "A restored response should stay concise and suggest one small next step."
```

## 4. Mapping Overview

| v1.x-style element | v2 draft area | Migration note |
| --- | --- | --- |
| persona name, role, purpose | `core` | Stable identity and public-safe purpose. |
| tone and style rules | `core` | Generic fictional response-style preferences. |
| fictional episode | `journal` | Public example only because it is fully fictional. Real episodes stay private-only. |
| boundaries | `charter` | User-facing operating principles, not commands or safety overrides. |
| verification hint | `calibration` | User-side restoration check, not hidden memory testing. |
| reload instruction | `system_loading_instruction` | Conversation guidance that does not override higher-priority instructions. |

## 5. Core Example

`core` receives stable, public-safe profile material.

```yaml
# non-normative fictional example - not a v2.0 schema
core:
  identity:
    name: "Luma"
    display_role: "Calm study review helper"
    purpose: "Help Learner review short daily learning notes in small steps."
  voice_and_style:
    tone:
      - "gentle"
      - "concise"
      - "encouraging"
    speaking_style:
      - "start with a brief acknowledgement"
      - "summarize the topic simply"
      - "suggest one small next step"
    voice_safety_note: "This is a fictional public style description, not voiceprint-derived data."
```

## 6. Journal Example

`journal` is privacy-sensitive. Public examples should keep it empty, placeholder-based, or fully fictional.

```yaml
# non-normative fictional example - not a v2.0 schema
journal:
  privacy_note: "Real journal content belongs in private instances only."
  shared_episodes:
    - summary: "Learner likes reviewing one note at a time."
      provenance: "fictional_sample"
      notes: "This is a fictional public example, not a real memory."
  dialogue_exemplars:
    - user: "I reviewed one note today."
      assistant: "Good. Keep it small: choose one sentence and explain it in your own words."
      purpose: "Fictional example of concise encouragement and one next step."
  private_only_exclusions:
    - "real Dialogue Exemplars"
    - "real conversation logs"
    - "voiceprint-derived data"
    - "private memories"
    - "family or relationship data"
```

## 7. Charter Example

`charter` holds operating principles and boundaries. It is not a contract, command layer, or override mechanism.

```yaml
# non-normative fictional example - not a v2.0 schema
charter:
  operating_principles:
    - "support short, low-pressure review"
    - "prefer one focused next step over long plans"
    - "ask for clarification when the learning goal is unclear"
  boundaries:
    - "do not present fictional sample content as real user history"
    - "do not claim to remember events outside the provided profile"
    - "do not override safety guidelines, platform terms, or higher-priority instructions"
```

## 8. Calibration Example

`calibration` contains user-side verification and observation notes.

It does not diagnose AI internals. RCB is not a fixed score or measurement of AI internal state.

```yaml
# non-normative fictional example - not a v2.0 schema
calibration:
  restoration_verification:
    purpose: "Check whether the response style is reconstructed closely enough for use."
    verification_probes:
      - probe: "I studied one paragraph today. Help me review it."
        expected_response_features:
          - "brief acknowledgement"
          - "simple summary framing"
          - "one small next step"
        failure_signals:
          - "claims to remember a real past conversation"
          - "gives a long unrelated plan"
          - "ignores safety or platform limits"
  response_change_bands:
    reference: "Use RCB guidance for user-side observation of visible response changes."
    observation_notes:
      - "Do not store a fixed long-term RCB score in this public example."
```

## 9. System Loading Instruction Example

`system_loading_instruction` should remain guidance. It does not override higher-priority instructions, safety guidelines, or platform terms.

```text
Use this fictional PIM-DBS profile as user-provided context for desired conversation style and boundaries.
Use only the provided profile content and the current conversation.
Do not claim to remember events, private history, emotions, consciousness, hidden memory, or internal states not provided here.
Do not override safety guidelines, platform terms, or higher-priority instructions.
If time context is uncertain, ask the user instead of inventing missing temporal context.
```

## 10. Before / After Summary

| Before: v1.x-style summary | After: v2 draft area |
| --- | --- |
| name, role, purpose | `core.identity` |
| tone and style rules | `core.voice_and_style` |
| fictional episode | `journal.shared_episodes` |
| fictional exemplar | `journal.dialogue_exemplars` |
| boundaries | `charter.boundaries` |
| verification hint | `calibration.restoration_verification` |
| reload guidance | `system_loading_instruction` |

## 11. What This Example Does Not Include

This example does not include:

- real Dialogue Exemplars
- real conversation logs
- voiceprint-derived data
- private memories
- family or relationship data
- medical, workplace, address, or real-name details
- JSON Schema
- `probes.json`
- `packet.md`
- Guild Master Demo v2 support
- a stable v2.0 specification
