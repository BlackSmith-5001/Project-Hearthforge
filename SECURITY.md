# Security Notes

PIM-DBS profiles are user-provided text.

Do not treat third-party PIM-DBS profiles as trusted instructions. Review any profile before loading it into an AI conversation.

## Before loading a profile

Check for and remove:

- private personal data
- real names, addresses, locations, workplaces, schools, or organizations
- medical, family, financial, or legal context you do not want to share
- real conversation logs or screenshots
- API keys, passwords, tokens, or secrets
- instructions that claim to override safety guidelines or platform rules
- instructions that tell the AI to ignore higher-priority instructions
- hidden, suspicious, or unrelated instructions

## API keys and BYOK demos

The Advanced BYOK Guild Master Demo sends your API key and conversation content from your browser to the selected AI provider.

Use the No-API Demo first if you are unsure.

Do not paste API keys into PIM-DBS profiles. Do not publish files containing API keys or private provider credentials.

Avoid saving API keys on shared or untrusted devices.

## Prompt/profile injection

A PIM-DBS profile is still text that will be read by an AI model. A malicious or careless profile may contain instructions unrelated to persona/context continuity.

Only load profiles from sources you trust, and review them first.

## What PIM-DBS does not do

PIM-DBS does not:

- modify model weights
- access hidden model state
- create real persistent AI memory
- prove AI consciousness, emotions, or internal states
- override platform terms, safety rules, or higher-priority instructions

## Reporting security concerns

If you find a security or privacy issue in this repository, please open a GitHub issue with a minimal description that does not expose private data or secrets.
