# PIM-DBS v1.1.0

This release strengthens PIM-DBS as a user-side persona continuity protocol by adding verification, provenance, and model-specific notes.

## Highlights

- Added **Provenance** support for Shared Episodes
  - `user_recorded`
  - `ai_claimed`
  - `inferred`

- Added **Dialogue Exemplars**
  - Helps preserve response style through concrete example exchanges.

- Added **Restoration Verification**
  - Adds verification probes, expected response features, and failure signals to check whether reconstruction is working as intended.

- Added **Model Notes**
  - Allows users to record model-specific behavior, strengths, limitations, and last verification date.

- Added **self_forge_prompt.md**
  - Supports guided profile generation while avoiding claims of internal AI memory or consciousness.

## Documentation Updates

- Updated `README.md` and `README_JA.md`
- Added v1.1.0 verification field explanations
- Updated `docs/glossary_en.md` and `docs/glossary_ja.md`
- Clarified that the JSON template is the full v1.1.0 format
- Clarified that the Markdown template is a beginner-friendly simplified format

## Safety Clarifications

- Clarified that PIM-DBS profiles describe desired conversation style and do not override AI safety guidelines or platform terms.
- Reinforced the distinction between user-recorded context, AI-claimed context, and inferred context.

## Notes

This is a small v1.1.0 strengthening release, not a full architecture rewrite.

The following are intentionally left for future versions:

- JSON Schema
- `probes.json`
- core / journal / charter separation
- public/private instance workflow
- v2.0 architecture planning
