# Response Change Bands Design Note

This note is a v1.5.2 candidate design memo for migrating the older CLI wording toward Response Change Bands (RCB).

It is not a formal guide yet. The goal is to prepare a safer vocabulary for v1.6.0 without changing the JSON template, README, Glossary, or existing public terminology in this step.

## 1. Why Move From CLI to RCB?

The older term CLI (Cognitive Load Index) has several problems:

- CLI is easy to misread as Command Line Interface.
- Cognitive Load Index can sound like it measures the AI model's internal cognitive load.
- Index suggests a precise metric, even though the signal is only an observation of output patterns.
- The 0-100% style can create false precision.

The old name should remain in project history, but future public guidance should move toward a safer operational term.

## 2. Definition

RCB means Response Change Bands.

RCB observes changes visible in the assistant's output. It does not diagnose model internals, emotional state, fatigue, consciousness, or memory.

RCB pairs naturally with the Response Change Catalog:

- the catalog names observable response changes
- RCB groups the short-term visibility of those changes into coarse bands

## 3. Observation Count

RCB uses a small observation count, not a percentage.

Suggested count rules:

- appearance of a listed response-change type: +1
- failure to preserve an already-stated premise: +1
- clear break in conversational rhythm: +2
- maximum count: 4

Use the count as a short-term conversational signal:

- do not judge from a single response alone
- look at a trend across 2-3 responses
- reset the count for each conversation
- do not treat it as a lifetime health score for the AI

## 4. Draft 0-4 Bands

| Count | Band | Meaning |
| --- | --- | --- |
| 0 | Clear | No notable response change is visible. |
| 1 | Ripple | A small response change is visible, but the conversation is still stable. |
| 2 | Drift | Multiple small changes, or one meaningful mismatch, are visible. |
| 3 | Disturbance | The response pattern is noticeably unstable or mismatched. |
| 4 | Storm | The conversation should be stopped or reset rather than pushed further. |

These names are metaphorical labels for user-side observation. They are not measurements of internal AI state.

## 5. User-side Responses by Band

| Band | User-side response |
| --- | --- |
| 0 Clear | Continue normally. |
| 1 Ripple | Avoid expanding the topic too much. Keep the next prompt simple. |
| 2 Drift | Focus on one topic, shorten the prompt, and restate the needed premise. |
| 3 Disturbance | Pause the thread, re-present the Temporal Anchor, or take a break. |
| 4 Storm | End the session or resume the next day. If needed, reload from the PIM-DBS profile. |

## 6. Terms to Avoid

Avoid wording that implies diagnosis or internal measurement:

- the AI is tired
- AI load
- weight of thought
- measurement
- diagnosis
- load rate 0-100%
- asking the AI to self-report its current load

Prefer output-focused wording:

- the response shows...
- the output pattern changed...
- the conversation rhythm appears...
- the previous premise was not preserved...

## 7. Candidate v1.6.0 Work

If RCB moves forward, v1.6.0 can include:

- Glossary: add RCB and mark CLI as deprecated
- README updates
- FAQ wording updates
- cross-links with the Response Change Catalog
- formal `response_change_bands_en.md` and `response_change_bands_ja.md` guides

## 8. Out of Scope

This design note does not include:

- JSON template changes
- JSON Schema
- `probes.json`
- calibration files
- core / journal / charter separation
- Guild Master Demo changes
- public real Dialogue Exemplars or real persona voiceprints
