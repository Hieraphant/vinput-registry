# asr.xifan.openai-compatible

Cloud ASR provider script for OpenAI-compatible `/v1/audio/transcriptions` endpoints.

## Entry

- `entry.py`

## Runtime

- command: `python3`
- input: raw PCM `S16_LE`, mono, `16000 Hz` via stdin
- output: final transcript via stdout

## Environment Variables

- `OPENAI_COMPATIBLE_ASR_API_KEY` required
- `OPENAI_COMPATIBLE_ASR_URL` optional
- `OPENAI_COMPATIBLE_ASR_BASE_URL` optional
- `OPENAI_COMPATIBLE_ASR_MODEL` optional
- `OPENAI_COMPATIBLE_ASR_LANGUAGE` optional
- `OPENAI_COMPATIBLE_ASR_PROMPT` optional
- `OPENAI_COMPATIBLE_ASR_RESPONSE_FORMAT` optional
- `OPENAI_COMPATIBLE_ASR_TEMPERATURE` optional
- `OPENAI_COMPATIBLE_ASR_TIMEOUT` optional

## Notes

- This resource is intended to be materialized into local config and executed locally.
- Configuration guidance for users should be derived from the env list above.
