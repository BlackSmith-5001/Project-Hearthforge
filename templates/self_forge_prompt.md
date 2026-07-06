# Self-Forge Prompt (PIM-DBS v1.1.0)

Use this prompt when you want an AI assistant to summarize the persona context and interaction style available in the current chat into the PIM-DBS JSON format.

```text
Please summarize the AI persona settings and interaction style using only the context shared in this chat.

Do not assume that the AI has internal memory, consciousness, emotions, or hidden states.
Treat all persona, memory, emotion, temperature, and relationship terms as user-side contextual descriptions and metaphors.

Organize the result in the PIM-DBS JSON format so that the user can reload it later as a context profile.
When possible, include Dialogue_Exemplars, Restoration_Verification probes, Model_Notes, and provenance for Shared_Episodes using one of: user_recorded, ai_claimed, inferred.

Use the following file as the target structure:
templates/pim-dbs_template.json

If some fields cannot be inferred from the current chat, write a neutral placeholder such as "<not specified in this chat>" instead of inventing details.
```
