# Self-Forge Guide

This guide explains how to use `templates/self_forge_prompt.md` safely.

Self-Forge is not a method for asking an AI to reveal internal memory, consciousness, emotions, or a soul. It is a helper workflow for drafting a PIM-DBS JSON profile from the context available in the current chat.

## 1. What Self-Forge is

Self-Forge is a guided profile-drafting step.

You give the AI the Self-Forge prompt, and the AI summarizes the persona settings, interaction style, and relevant context that are visible in the current conversation. The output should be treated as a draft for the user to review.

## 2. Before you begin

Before using Self-Forge, decide whether the output will be private or public.

If the chat contains real names, private memories, workplace details, medical or family matters, inside jokes, or real conversation excerpts, treat the resulting profile as a private instance. For sharing decisions, see [Public / Private Guide](public_private_guide_en.md).

## 3. How to use `self_forge_prompt.md`

Open `templates/self_forge_prompt.md` and copy the prompt into the current chat.

Ask the AI to use only the context already shared in that chat. If the AI cannot infer a field, it should use a neutral placeholder rather than inventing details.

The intended output is a PIM-DBS JSON draft that follows `templates/pim-dbs_template.json`.

## 4. How to review the generated JSON

After the AI generates JSON, review it before saving or reloading it.

Check that:

- the JSON structure is valid
- the profile describes user-side context, not AI internal state
- sensitive details have been removed or kept private
- placeholders are used where the chat did not provide enough information
- the `System_Loading_Instruction` does not override platform rules or safety guidelines

For the section structure, see [JSON Guide](json_guide_en.md).

## 5. Check Provenance

Review every `Shared_Episodes` item and confirm its `Provenance` value.

Use:

- `user_recorded` for context directly recorded by the user
- `ai_claimed` for claims made by the AI
- `inferred` for summaries or interpretations

Do not allow inferred or AI-claimed content to appear as verified user-recorded fact.

## 6. Check Dialogue Exemplars

Review `Dialogue_Exemplars` as style references.

They should show tone, pacing, boundaries, or recurring phrases. They should not contain private chat excerpts unless the profile will remain private.

Remove any example that exposes another person, sensitive context, or private relationship details.

## 7. Set Restoration Verification

Review or add `Restoration_Verification` probes before using the profile.

A good probe checks whether the reloaded profile reflects the intended tone, role, boundaries, and key context. It should also include failure signals, such as unsafe claims, over-literal interpretation, or ignoring user-defined boundaries.

These checks verify reconstruction quality, not hidden memory.

## 8. Do not treat AI-generated content as fact

Self-Forge output is a draft.

The AI may summarize incorrectly, overstate continuity, invent details, or describe its own behavior too literally. The user is responsible for reviewing, correcting, deleting, or marking those details with the correct provenance.

Never treat AI-generated claims about internal memory, consciousness, emotions, or hidden state as verified fact.

## 9. Public / private reminder

Before publishing or sharing a generated profile, review it as a private instance.

Remove real names, workplaces, addresses, medical details, family circumstances, real chat logs, inside jokes, and unverified AI self-claims. When in doubt, keep it private.

See [Public / Private Guide](public_private_guide_en.md).

## 10. JSON Guide

Self-Forge creates a draft, but the JSON Guide explains what each section means.

After generating a profile, use [JSON Guide](json_guide_en.md) to review the structure, reload process, verification fields, and privacy reminders.
