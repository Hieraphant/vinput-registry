# providers.openai-compatible.batch

Cloud ASR provider script for OpenAI-compatible `/v1/audio/transcriptions` endpoints.

## Entry

- `entry.py`

## Runtime

- command: `python3`
- input: raw PCM `S16_LE`, mono, `16000 Hz` via stdin
- output: final transcript via stdout

## Environment Variables

- `VINPUT_ASR_API_KEY` required
- `VINPUT_ASR_URL` optional
- `VINPUT_ASR_BASE_URL` optional
- `VINPUT_ASR_MODEL` optional
- `VINPUT_ASR_LANGUAGE` optional
- `VINPUT_ASR_PROMPT` optional
- `VINPUT_ASR_RESPONSE_FORMAT` optional
- `VINPUT_ASR_TEMPERATURE` optional
- `VINPUT_ASR_TIMEOUT` optional

## Notes

- This resource is intended to be materialized into local config and executed locally.
- Configuration guidance for users should be derived from the env list above.
