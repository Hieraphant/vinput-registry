# vinput-registry

Registry repository for vinput resources.

## Layout

- `registry/`: top-level resource indexes
- `i18n/`: resource display text, one file per language
- `resources/`: script resources, one directory per resource id

## Resource Rules

- Resource ids follow `<kind>.<author>.<name>`
- Download-related URLs use array form for fallback
- Resource display text is stored in i18n files as:
  - `<id>.title`
  - `<id>.description`
- Script resources should keep:
  - `entry.py`
  - `README.md`

## Current Scope

- `models.json`: local ASR models
- `asr-providers.json`: cloud ASR provider scripts
- `llm-adaptors.json`: managed local LLM adaptor scripts
