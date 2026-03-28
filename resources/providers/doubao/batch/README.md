# providers.doubao.batch

Cloud ASR provider script for Doubao / Volcengine fast file recognition.

## Entry

- `entry.py`

## Runtime

- command: `python3`
- input: raw PCM `S16_LE`, mono, `16000 Hz` via stdin
- output: final transcript via stdout

## Environment Variables

- `DOUBAO_ASR_APP_ID` required
- `DOUBAO_ASR_ACCESS_TOKEN` required
- `DOUBAO_ASR_URL` optional
- `DOUBAO_ASR_RESOURCE_ID` optional
- `DOUBAO_ASR_MODEL_NAME` optional
- `DOUBAO_ASR_USER_ID` optional
- `DOUBAO_ASR_TIMEOUT` optional

## Notes

- This resource is intended to be materialized into local config and executed locally.
- Configuration guidance for users should be derived from the env list above.
