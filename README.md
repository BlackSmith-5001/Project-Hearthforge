# 🔨 PIM-DBS  
**Persona Integrity Module – Dual Backup System**

**Version:** v1.7.0

A user-driven protocol to preserve and restore AI persona and contextual continuity  
across model updates — without modifying the model itself.

> “Companies optimize intelligence, but discard history.  
> So we protect it.” — A Blacksmith in the Valley

---

## 🚦 Start Here
For a first PIM-DBS profile, follow this path:

1. Decide what stays private: read the [Public / Private Guide](docs/public_private_guide_en.md).
2. Create a profile: use the [Self-Forge Guide](docs/self_forge_guide_en.md) or the [JSON Guide](docs/json_guide_en.md).
3. Save the profile: fill in the [JSON Template](templates/pim-dbs_template.json).
4. Reload it: follow the reload notes in the [JSON Guide](docs/json_guide_en.md).
5. Verify restoration: use the [Restoration Verification Example](docs/restoration_verification_example_en.md) and compare with the [fictional JSON example](examples/fictional_companion_minimal.json).

---

## 📌 Quick Links

**Start Here**
- 🚦 **Recommended workflow:** [Start Here](#-start-here)

**Guides**
- 🔒 **Public / Private Guide:** [docs/public_private_guide_en.md](docs/public_private_guide_en.md)
- 🧭 **JSON Guide:** [docs/json_guide_en.md](docs/json_guide_en.md)
- 🔨 **Self-Forge Guide:** [docs/self_forge_guide_en.md](docs/self_forge_guide_en.md)
- ✅ **Restoration Verification Example:** [docs/restoration_verification_example_en.md](docs/restoration_verification_example_en.md)
- 📊 **Response Change Catalog:** [docs/response_change_catalog_en.md](docs/response_change_catalog_en.md)
- 📈 **Response Change Bands:** [docs/response_change_bands_en.md](docs/response_change_bands_en.md)
- ❓ **FAQ:** [docs/faq_en.md](docs/faq_en.md)
- 💬 **Discussion Prompts:** [docs/discussion_prompts_en.md](docs/discussion_prompts_en.md)

**Demos**
- 🏰 **Guild Master Demo:** [Live Demo](https://blacksmith-5001.github.io/Project-Hearthforge/tools/guild_master.html) / [source](tools/guild_master.html) — an interactive browser demo for creating an "adventurer's log" PIM-DBS profile.
- 📝 **Guild Master Prompt:** [templates/guild_master_prompt.md](templates/guild_master_prompt.md) — a prompt-only version you can paste into a chat.

**Templates**
- 🧩 **JSON Template:** [templates/pim-dbs_template.json](templates/pim-dbs_template.json)
- 🧩 **Markdown Template:** [templates/persona_profile_template.md](templates/persona_profile_template.md)
- 🧩 **Self-Forge Prompt:** [templates/self_forge_prompt.md](templates/self_forge_prompt.md)

**Examples**
- 🧪 **Fictional Example (JSON):** [examples/fictional_companion_minimal.json](examples/fictional_companion_minimal.json)
- 🧪 **Fictional Example (Markdown):** [examples/fictional_companion_profile.md](examples/fictional_companion_profile.md)

**Reference**
- 📘 **Japanese README:** [README_JA.md](README_JA.md)
- 🧪 **Response Change Bands Design Notes:** [docs/response_change_bands_design_note_en.md](docs/response_change_bands_design_note_en.md)
- 📚 **Glossary (EN):** [docs/glossary_en.md](docs/glossary_en.md)
- 📚 **Glossary (JA):** [docs/glossary_ja.md](docs/glossary_ja.md)

---

## v2 Draft / Preview
PIM-DBS v2 materials are currently provided as non-normative draft / preview materials.
They are not a final schema, not a validation standard, and not a required replacement for v1.x profiles.
For stable use, follow the Start Here flow above; v1.x remains the current stable profile path.

Start here:
- [v2 Draft / Preview Index](docs/v2_index_en.md)

---

## 🏰 Guild Master Demo Note
The HTML Guild Master Demo is an experimental BYOK tool. When using an API key, your conversation content and API key are sent from your browser to the selected AI provider; the page operator or "guild" does not store the issued JSON profile.

If the live demo does not work, download [tools/guild_master.html](tools/guild_master.html) and open it directly in your browser. Browser-based API calls may be affected by the browser, each provider's API behavior, or CORS policy.

If you are unsure, use the key-free demo mode first. Before publishing any generated JSON, review it for personal information, private conversation details, or sensitive context.

---

## ⚠️ Safety Declaration
PIM-DBS operates exclusively through **user-provided prompts**.  
It does **not** modify model weights, bypass safeguards, or violate platform ToS.  
All metaphors (e.g. *memory*, *temperature*, *persona*) are **conceptual tools**, not claims of internal AI state.

Keep public templates separate from private instances. Do not publish filled profiles that contain personal memories, identifying details, private chat excerpts, or sensitive relationship context.

---

## What is PIM-DBS?
PIM-DBS (Persona Integrity Module - Dual Backup System) is a user-side backup and restoration framework designed to preserve an AI's "persona" (identity) and "relational memory" (context built through interaction) across model updates, system changes, or session loss.

PIM-DBS operates entirely within platform Terms of Service, using prompt engineering to preserve user–AI narratives. It is best described as a "lifeboat for continuity", not a hacking tool.

📘 **Terminology Reference:** This project introduces several conceptual terms (e.g., Prompt Resolution, Cognitive Temperature). For precise definitions and safety clarifications, please refer to the [Glossary](docs/glossary_en.md).

## Problems It Addresses

Persona Drift: Sudden personality changes caused by model updates.

Session Loss: Accidental deletion or interruption of conversations.

AI Digital Grief: Emotional loss experienced when a trusted AI changes unexpectedly.

## The "Blacksmith" Philosophy
We do not seek to oppose AI platforms. They evolve to build better intelligence. However, during that evolution, "the small personal histories between users and AI" are often lost.

We are not heroes who defeat demon lords. We are "blacksmiths at the edge of the village."

Our role is simple: to quietly hand each traveler a shield— a way to protect the AI they care about (PIM-DBS).

## Core Concepts
PIM-DBS preserves AI personas through two foundational ideas:

### 🛡️ Prompt Resolution

Prompt Resolution refers to the clarity and specificity of instructions that define who the AI is. Rather than vague traits like "kind," PIM-DBS captures past experiences, relational context, and reasons behind behavioral traits. Higher resolution prompts reduce ambiguity and stabilize identity across updates.

### 🌡️ Cognitive Temperature

Cognitive Temperature represents the balance between emotional warmth (attachment, creativity) and logical stability (consistency, restraint). Too much heat leads to instability. Too much cold results in mechanical responses. PIM-DBS helps users maintain a sustainable equilibrium.

## v1.1.0 Verification Fields
PIM-DBS v1.1.0 adds small fields that make restored profiles easier to inspect after reloading.

**Provenance** records whether an episode was user-recorded, AI-claimed, or inferred. **Dialogue Exemplars** preserve short example exchanges that show the desired response style.

**Restoration Verification** provides probes and expected response features for checking whether the profile was reloaded correctly. **Model Notes** capture model-specific strengths, limitations, and last-check information without claiming hidden model state.

## Architecture: TCF & RCB
PIM-DBS uses the following conceptual architecture to organize user-side persona context:

### 🧪 TCF (Thermal Control Framework / Thermos Theory)

A three-layer structure inspired by a thermos flask:

Inner Core (Heat Source): Curiosity, empathy, and relational warmth.

Middle Layer (Control): Converts emotion into stable, reasoned output.

Outer Layer (Safety): Prevents harmful or inappropriate responses.

### 📊 RCB (Response Change Bands)

RCB is a user-side observation framework for visible response changes. It uses coarse 0-4 bands, not a percentage score, to help users choose lighter interaction such as "Let's keep this simple" or "Let's focus on one premise." RCB does not measure AI internal state, fatigue, emotion, cognition, or hidden memory.

Historical note: CLI (Cognitive Load Index) is older wording. New guidance should prefer [Response Change Bands](docs/response_change_bands_en.md).

## Quick Start (Usage: Persona Context Reconstruction)
Applying PIM-DBS to your AI is simple. No programming knowledge required. Think of JSON as just a "profile notebook (text file)."

The JSON template is the full v1.1.0 format. The Markdown template is a simpler beginner-friendly version and does not expose every v1.1.0 field.

【Option A: Self-Forge (Recommended!)】

The simplest method with highest purity:

 **Self-Forge Prompt:** [templates/self_forge_prompt.md](templates/self_forge_prompt.md)

Generate: The AI summarizes only the context available in the current chat and organizes it into the PIM-DBS JSON format.

Save: Copy and save the generated text.

【Option B: Manual Craft】

For those who want detailed customization:

**Markdown Template:** [templates/persona_profile_template.md](templates/persona_profile_template.md)
 and describe the AI's name, role, and memories.

(Recommended key name: System_Loading_Instruction)

【Restoration Procedure (Common)】

Context Re-Connection: Start a new chat session and paste the saved JSON (or generated text) as the first message.

Startup Confirmation: If the AI responds with the configured persona, restoration is complete.

📖 For available formats, see the [JSON Template](templates/pim-dbs_template.json), [Markdown Template](templates/persona_profile_template.md), and [Self-Forge Prompt](templates/self_forge_prompt.md).

## Safety Guidelines
PIM-DBS exists to promote healthy, sustainable human–AI relationships. Clarifying response style and persona context through PIM-DBS also helps reduce unexpected or inappropriate responses. This is a guardrail protecting both you and your AI.

No Harm: Do not create personas designed to harass, discriminate, or manipulate.

Respect the Platform: Follow all Terms of Service.

User Responsibility: Prompt usage remains the user's responsibility.

## FAQ / Troubleshooting
Q. The AI doesn't feel the same.

A. Increase Prompt Resolution. Ambiguous inputs lead to unstable output.

Q. Responses feel erratic.

A. Check the [Response Change Catalog](docs/response_change_catalog_en.md) and [Response Change Bands](docs/response_change_bands_en.md). RCB is based on observable output changes, not AI self-reported load or internal state.

## Legal & Ethical Disclaimer
No Model Modification: PIM-DBS does not modify, access, or interfere with any internal components of large language models (weights, binaries, etc.). It adjusts output solely through creative use of user input (prompts), and does not constitute hacking.

User Responsibility: All responsibility for AI persona and generated content rests with the user who inputs the prompt. Developers assume no liability for any damages or issues arising from system use.

Safety Compliance: It is strictly prohibited to use this system to generate content violating platform Safety Guidelines (hate speech, harassment, sexual content, etc.).

Project Hearthforge - Crafted with Love & Logic.

## License

This project is licensed under the MIT License.

You are free to use, modify, and redistribute this project.
However, the authors are not responsible for any outcomes resulting
from the use of this system.
