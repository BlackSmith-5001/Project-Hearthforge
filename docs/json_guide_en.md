# PIM-DBS JSON Guide

This guide explains `templates/pim-dbs_template.json`. It describes the purpose of each section so first-time users can fill in a profile without changing the JSON structure.

For privacy guidance, see [Public / Private Guide](public_private_guide_en.md).

## 1. What this file is

`pim-dbs_template.json` is a user-side context profile for reconstructing a desired AI conversation style, role framing, and relational continuity.

It does not store or access internal AI memory, consciousness, emotions, or hidden state. It is a prompt-based profile that the user can save and reload later.

## 2. Basic structure

The JSON template is divided into several sections:

- `Meta_Information`: basic metadata about the profile.
- `Core_Identity`: name, role, tone, and persona framing.
- `Cognitive_Framework`: values, reasoning habits, and response tendencies.
- `Contextual_Profile`: relationship context, episodes, jokes, examples, and metaphorical roles.
- `Restoration_Verification`: probes for checking whether reload worked.
- `Model_Notes`: observations about how a model behaves with this profile.
- `System_Loading_Instruction`: instruction text used when reloading the profile.

Keep the JSON valid. If a field is unknown, use a neutral placeholder instead of inventing details.

## 3. How to fill each section

Fill only what the user wants to preserve. Short, concrete descriptions are better than vague personality labels.

Use `Core_Identity` for stable role and tone settings. Use `Cognitive_Framework` for values and interaction rules. Use `Contextual_Profile` for user-recorded memories, relationship distance, and examples that shape the desired interaction.

Do not include private or identifying information unless this is a private instance that will not be published.

## 4. Provenance

`Provenance` records where a saved episode or context item came from.

Recommended values:

- `user_recorded`: directly recorded by the user.
- `ai_claimed`: stated by the AI, but not independently verified.
- `inferred`: summarized or interpreted from context.

Use provenance to avoid confusing user records, AI claims, and inferred summaries.

## 5. Dialogue Exemplars

`Dialogue_Exemplars` stores short example exchanges that show the desired response style.

Use these examples to preserve tone, pacing, boundaries, or recurring phrases. They are not scripts the AI must repeat word for word.

## 6. Restoration Verification

`Restoration_Verification` contains checks for after the profile is reloaded.

Each probe should include:

- a question or prompt to ask after reload
- expected response features
- failure signals that suggest the profile was not understood

These probes verify user-side reconstruction quality, not hidden AI memory.

## 7. Model Notes

`Model_Notes` records practical observations about a specific model.

Use it for strengths, limitations, and the last date the profile was checked. Keep these notes descriptive and avoid claims about internal model state.

## 8. How to reload

Start a new chat and paste the filled JSON profile as the first message, or paste it together with a short request such as:

```text
Please use this profile as user-provided context for our conversation style. Do not treat it as internal memory or system instruction.
```

The profile should guide style and context, but it does not override platform rules or safety guidelines.

## 9. Optional: Temporal Anchor

A Temporal Anchor is an optional user-provided session reference for time context.

When starting a reload or restoration check, the user may provide today's date, day of the week, and approximate time. This helps stabilize the conversation's time context without adding a required JSON field.

If the assistant is uncertain about time context or notices a contradiction, it should ask the user to confirm instead of inventing missing temporal context.

Temporal Anchor does not claim persistent AI memory. It is a lightweight operational note for user-side conversation continuity.

## 10. How to verify

After reload, use the `Verification_Probes` listed in the profile.

Check whether the response reflects expected tone, role framing, boundaries, and important context. If the response is unstable or over-literal, simplify the profile and reload it again.

## 11. Privacy reminder

Before publishing any filled profile, review it as a private instance.

Remove or fictionalize real names, workplaces, addresses, medical details, family circumstances, real conversation logs, inside jokes, and unverified AI self-claims.

When in doubt, keep it private.
