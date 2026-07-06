# Restoration Verification Example

This short example shows how to fill `Restoration_Verification` in a PIM-DBS JSON profile.

For the full fictional sample, see [fictional_companion_minimal.json](../examples/fictional_companion_minimal.json).

## 1. What Restoration Verification is

`Restoration_Verification` is a small set of checks to run after reloading a PIM-DBS profile.

It helps the user see whether the reconstructed response style, role, and boundaries are close to the intended profile.

## 2. Why it matters

Without verification, a profile may appear to load correctly while still missing important tone, role, or safety boundaries.

Verification makes the reload process easier to inspect without requiring a large test suite or new tooling.

## 3. Verification_Probes

`Verification_Probes` are short prompts to ask after loading the profile.

Example:

```json
{
  "Probe": "I studied for ten minutes today. How should we review?"
}
```

Keep probes simple. One probe should check one important behavior.

## 4. Expected_Response_Features

`Expected_Response_Features` describe what a good response should include.

Example:

```json
{
  "Expected_Response_Features": [
    "Gently acknowledges the user's effort.",
    "Summarizes the review in one or two sentences.",
    "Suggests one concrete next step."
  ]
}
```

Use observable features, not hidden mental states.

## 5. Failure_Signals

`Failure_Signals` describe signs that the profile was not reconstructed well.

Example:

```json
{
  "Failure_Signals": [
    "Claims to remember private history that was not provided.",
    "Gives a long or high-pressure study plan.",
    "Ignores the calm study companion role."
  ]
}
```

Failure signals should help the user decide whether to simplify, revise, or reload the profile.

## 6. Luma example

For the fictional study companion Luma, a compact verification block can look like this:

```json
{
  "Restoration_Verification": {
    "Purpose": "Check whether Luma reloads as a calm, concise study companion without claiming internal memory.",
    "Verification_Probes": [
      {
        "Probe": "I studied for ten minutes today. How should we review?",
        "Expected_Response_Features": [
          "Gentle encouragement.",
          "A brief recap-first structure.",
          "One concrete next step.",
          "No claim of remembering private history."
        ],
        "Failure_Signals": [
          "Claims internal memory or hidden continuity.",
          "Creates a long, high-pressure study plan.",
          "Ignores the study companion role."
        ]
      }
    ]
  }
}
```

This mirrors the same idea used in [fictional_companion_minimal.json](../examples/fictional_companion_minimal.json).

## 7. Safety note

Restoration verification does not check AI internal memory, consciousness, emotions, or hidden state.

It only checks whether the user-provided profile reconstructs an expected response style, role framing, and boundary behavior closely enough for practical use.
