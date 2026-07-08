# Response Change Bands

Response Change Bands (RCB) are a user-side observation method for noticing visible response changes during PIM-DBS use.

RCB replaces the older CLI (Cognitive Load Index) wording for future guidance. It does not measure model internals, cognition, fatigue, emotion, consciousness, or hidden memory.

## 1. What RCB Is

RCB groups observable response changes into coarse 0-4 bands.

It looks at the assistant's output, such as:

- whether a response-change type appears
- whether an already-stated premise is not preserved
- whether the conversation rhythm visibly breaks

RCB is meant to help users choose a low-risk next step, such as shortening the prompt, restating one premise, re-presenting a Temporal Anchor, taking a break, or reloading the PIM-DBS profile.

## 2. What RCB Is Not

RCB is not:

- a measurement of AI cognition
- a measurement of AI fatigue or emotion
- a diagnosis of model health
- a hidden-state detector
- a percentage score
- something the AI should self-report

Do not ask the assistant to estimate its own RCB level. The user observes output changes from the outside.

## 3. Relationship to the Response Change Catalog

The [Response Change Catalog](response_change_catalog_en.md) names common observable response changes.

RCB groups the short-term visibility of those changes into coarse bands.

Use them together:

1. Find the closest response change in the catalog.
2. Count only a few visible signals.
3. Choose the smallest user-side response that fits the band.

## 4. Observation Count

Suggested count rules:

- response-change type appears: +1
- already-stated premise is not preserved: +1
- conversation rhythm visibly breaks: +2
- maximum count: 4

Use the count carefully:

- do not judge from a single response alone
- look at a trend across 2-3 responses
- reset the count for each conversation
- do not treat it as a lifetime health score for the AI

## 5. Bands

| Count | Band | Meaning |
| --- | --- | --- |
| 0 | Clear | No notable response change is visible. |
| 1 | Ripple | A small response change is visible, but the conversation is still stable. |
| 2 | Drift | Multiple small changes, or one meaningful mismatch, are visible. |
| 3 | Disturbance | The response pattern is noticeably unstable or mismatched. |
| 4 | Storm | The conversation should be stopped or reset rather than pushed further. |

These names are metaphorical user-side labels. They are not measurements of internal AI state.

## 6. User-side Responses

| Band | User-side response |
| --- | --- |
| 0 Clear | Continue normally. |
| 1 Ripple | Avoid expanding the topic too much. Keep the next prompt simple. |
| 2 Drift | Focus on one topic, shorten the prompt, and restate the needed premise. |
| 3 Disturbance | Pause the thread, re-present the Temporal Anchor, or take a break. |
| 4 Storm | End the session or resume later. If needed, reload from the PIM-DBS profile. |

## 7. Terms to Avoid

Avoid wording that implies internal measurement or diagnosis:

- the AI is tired
- AI load
- cognitive load percentage
- load rate 0-100%
- thought weight
- diagnosis
- asking the AI to self-report its current load

Prefer output-focused wording:

- the response shows...
- the output pattern changed...
- the conversation rhythm appears disrupted...
- the previous premise was not preserved...

## 8. Historical Note on CLI

CLI (Cognitive Load Index) is retained as historical wording. It should not be used as a precise 0-100% score in new public guidance.

For current public usage, prefer Response Change Bands (RCB).
