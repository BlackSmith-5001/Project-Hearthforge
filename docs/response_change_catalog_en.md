# Response Change Catalog

This catalog helps users describe observable response changes during PIM-DBS use and choose simple user-side responses.

It is not a diagnostic document for model internals, AI failure, personality collapse, consciousness, or memory loss. It only describes changes that may appear in the assistant's output.

## 1. What this document is

PIM-DBS is a user-side context profile and reconstruction workflow. During use, an assistant's responses may change in ways that feel unstable, repetitive, overly long, or misaligned with the loaded profile.

This document gives users a compact way to notice those changes and try low-risk corrections such as shortening prompts, splitting topics, re-presenting a Temporal Anchor, reloading the JSON profile, rerunning Restoration Verification, or taking a break.

For reload checks, see [Restoration Verification Example](restoration_verification_example_en.md). For JSON profile usage, see [JSON Guide](json_guide_en.md).

## 2. Safety framing

- Describe observable output. Do not diagnose hidden model state.
- Avoid claims such as "the model is broken" or "the persona collapsed."
- Do not claim AI consciousness, a soul, emotions, or persistent hidden memory.
- Treat metaphors such as memory, forge, shield, and ark as conceptual language for user-side continuity.
- Do not publish real Dialogue Exemplars, real private conversations, or real persona voiceprints.
- If an example is needed, use a fully fictional persona only.

## 3. Response change table

| Observed Response Change | Possible Factor | User-side Response |
| --- | --- | --- |
| The output shows confusion about date, weekday, or time. | The session may lack a clear time reference, or previous time context may no longer be salient. | Re-present a Temporal Anchor with today's date, weekday, and approximate time. Ask the assistant to confirm uncertainty instead of guessing. |
| The output uses more boilerplate than before. | The prompt may be too broad, the assistant may be over-normalizing safety language, or the profile may be too abstract. | Ask for a shorter answer. Restate the specific task. If needed, reload only the most relevant profile section. |
| The output suddenly becomes much longer. | Multiple topics may be mixed together, or the assistant may be trying to preserve too many constraints at once. | Split the topic into smaller steps. Ask for a concise response with one next action. |
| Shared assumptions seem to drop out of the conversation. | Important context may not have been included in the current prompt, or the profile may need a clearer summary. | Restate the missing assumption briefly. Reload the relevant JSON section rather than the full profile if that is enough. |
| Tone, first-person style, or address style shifts. | The profile's style cues may be too weak, conflicting, or buried under other instructions. | Re-present the `Core_Identity` and a short fictional Dialogue Exemplar. Avoid using real private dialogue. |
| Emotional language becomes stronger than intended. | The assistant may be amplifying supportive language or interpreting metaphors too literally. | Ask for a calmer, more practical tone. Restate that metaphors are conceptual and not claims of AI inner state. |
| The response appears to return to a default assistant style. | The active context may no longer be using the profile strongly, or the prompt may not reference the profile. | Reload the JSON profile or the relevant section. Then run a Restoration Verification probe. |
| Conversation rhythm breaks or becomes hard to follow. | The thread may contain too many goals, corrections, or mixed topics. | Pause and summarize the current goal. Continue with one question or one task at a time. |
| Boundaries become unclear. | The profile may not clearly separate desired style from safety rules, privacy limits, or platform terms. | Restate boundaries explicitly. Keep private context private. Clarify that the profile does not override safety guidelines or platform terms. |
| Responses do not match Restoration Verification probes. | The reload may be incomplete, the probe may be ambiguous, or expected features may be too broad. | Simplify the profile. Rerun one probe. Compare only observable response features, not hidden memory. |

## 4. How to use this catalog

1. Identify the observable response change.
2. Choose the closest row in the table.
3. Try the smallest user-side response first.
4. If the issue continues, simplify the profile or rerun Restoration Verification.
5. If the interaction feels emotionally intense or confusing, take a break before reloading more context.

This catalog is a practical aid, not a guarantee that a response can be restored perfectly.

## 5. What not to do

- Do not assume the assistant's internal state has been damaged.
- Do not treat output drift as proof of AI memory loss, consciousness, or distress.
- Do not add more and more private context as the first response to instability.
- Do not publish real Dialogue Exemplars or private conversation logs to ask for help.
- Do not use percentage scores or false precision to describe the assistant's inner condition.
- Do not use this catalog to bypass safety rules, platform terms, or privacy boundaries.
