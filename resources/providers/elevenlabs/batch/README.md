# providers.elevenlabs.batch

Cloud ASR provider script for the ElevenLabs speech-to-text API.

## Entry

- `entry.py`

## Runtime

- command: `python3`
- input: raw PCM `S16_LE`, mono, `16000 Hz` via stdin
- output: final transcript via stdout

## Environment Variables

- `ELEVENLABS_API_KEY` required
- `ELEVENLABS_MODEL_ID` optional
- `ELEVENLABS_LANGUAGE` optional
- `ELEVENLABS_URL` optional
- `ELEVENLABS_TIMEOUT` optional

## Notes

- This resource is intended to be materialized into local config and executed locally.
- Configuration guidance for users should be derived from the env list above.
