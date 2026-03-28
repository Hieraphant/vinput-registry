# vinput-registry

Registry repository for vinput resources.

## Layout

- `registry/`: top-level resource indexes
- `i18n/`: resource display text, one file per language
- `resources/providers/<folder>/<name>/`: cloud ASR provider scripts
- `resources/adapters/<folder>/<name>/`: managed local adaptor scripts

## Resource Rules

- Resource ids are stable machine identifiers.
- Resource ids should follow `<kinds>.<folder>.<name>`.
- `short_id` is required for every resource item.
- `short_id` is only for human interaction in CLI/GUI/logs.
- `short_id` must not be used for storage paths, download paths, or internal
  resource resolution.
- Download-related URLs use array form for fallback
- Resource display text is stored in i18n files as:
  - `<id>.title`
  - `<id>.description`
- Script resources should keep:
  - `entry.py`
  - `README.md`

## Resource Fields

All resource items should contain:

- `id`: stable machine identifier
- `short_id`: short human-facing identifier

Provider items additionally contain:

- `stream`: `true` for streaming scripts, `false` for one-shot scripts

## Current Scope

- `models.json`: local ASR models
- `providers.json`: cloud ASR provider scripts
- `adapters.json`: managed local LLM adapter scripts

## `vinput_model` Rules

For local ASR models, `vinput_model` is runtime-facing metadata and should use
the following top-level shape:

- `backend`: local backend selector such as `sherpa-offline` or
  `sherpa-streaming`
- `runtime`: `online` or `offline`
- `family`: `sherpa-onnx` C API family name
- `recognizer`: recognizer config fields
- `model`: model config fields

Field naming should stay as close as possible to `sherpa-onnx` C API naming.

## Terminology

- `models`: local ASR model assets
- `providers`: cloud ASR service scripts
- `adapters`: managed local LLM adaptor scripts
- `backend`: local ASR engine/backend selector for model runtime metadata
