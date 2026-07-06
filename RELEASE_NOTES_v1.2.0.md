# PIM-DBS v1.2.0

This release strengthens PIM-DBS as a first-time-user operations guide release.

It focuses on clearer onboarding, safer public/private handling, profile creation guidance, and practical restoration checks without changing the core architecture.

## Highlights

- Added **Public / Private Guides**
  - `docs/public_private_guide_en.md`
  - `docs/public_private_guide_ja.md`
  - Helps users distinguish public templates and fictional samples from private filled profiles.

- Added **JSON Guides**
  - `docs/json_guide_en.md`
  - `docs/json_guide_ja.md`
  - Explains how to fill `templates/pim-dbs_template.json` without changing the JSON structure.

- Added **Self-Forge Guides**
  - `docs/self_forge_guide_en.md`
  - `docs/self_forge_guide_ja.md`
  - Explains Self-Forge as a helper workflow for drafting a persona profile from the current chat context.

- Added **fictional example persona**
  - `examples/fictional_companion_minimal.json`
  - `examples/fictional_companion_profile.md`
  - Provides a beginner-friendly, fully fictional study companion example named Luma.

- Added **Restoration Verification Examples**
  - `docs/restoration_verification_example_en.md`
  - `docs/restoration_verification_example_ja.md`
  - Shows short examples for `Verification_Probes`, `Expected_Response_Features`, and `Failure_Signals`.

## README Updates

- Added a **Start Here** workflow to `README.md` and `README_JA.md`.
- Grouped Quick Links into:
  - Start Here
  - Guides
  - Templates
  - Examples
  - Reference

## Safety and Scope

- Reinforced public/private separation for profiles that may contain personal or sensitive context.
- Clarified that restoration checks evaluate reconstructed response style and boundaries, not AI internal memory or consciousness.
- This release does not include v2.0 architecture changes.

## Notes

PIM-DBS v1.2.0 is an operations-guide strengthening release, not a structural redesign.

The following are intentionally left for future versions:

- JSON Schema
- `probes.json`
- core / journal / charter separation
- v2.0 architecture planning
