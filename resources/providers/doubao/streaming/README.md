# providers.doubao.streaming

Cloud ASR provider script for Doubao ASR Realtime on Volcengine AI Gateway.

## Entry

- `entry.py`

## Runtime

- command: `python3`
- input: JSONL via stdin
- output: JSONL via stdout
- diagnostics: stderr only
- dependencies: Python standard library only

## Input Protocol

- `{"type":"audio","audio_base64":"...","commit":false}`
- `{"type":"audio","audio_base64":"...","commit":true}`
- `{"type":"finish"}`
- `{"type":"cancel"}`

`audio_base64` should contain mono `S16_LE` PCM at `16000 Hz`.

## Output Protocol

- `{"type":"session_started","session_id":"..."}`
- `{"type":"partial","text":"..."}`
- `{"type":"final","text":"..."}`
- `{"type":"final_timestamps","text":"...","words":[...]}`
- `{"type":"error","message":"..."}`
- `{"type":"closed"}`

## Environment Variables

- `VINPUT_ASR_API_KEY` required
  Bearer token sent in the `Authorization` header.
- `VINPUT_ASR_URL` optional
  Full Doubao realtime websocket URL. Overrides the default endpoint.
- `VINPUT_ASR_MODEL` optional
  Doubao realtime ASR model id.
- `VINPUT_ASR_TIMEOUT` optional
  Network timeout in seconds.
- `VINPUT_ASR_FINISH_GRACE_SECS` optional
  Extra wait time after local `finish` before the script closes the socket.
- `VINPUT_ASR_RESOURCE_ID` optional
  Optional upstream resource selector passed as `X-Api-Resource-Id`.
- `VINPUT_ASR_RESULT_TYPE` optional
  Provider-specific result mode forwarded in the session update payload.
- `VINPUT_ASR_ENABLE_VAD` optional
  Enables Doubao server-side VAD.
- `VINPUT_ASR_VAD_THRESHOLD` optional
  VAD sensitivity threshold passed to Doubao.
- `VINPUT_ASR_VAD_PREFIX_PADDING_MS` optional
  Milliseconds of audio padding preserved before speech start.
- `VINPUT_ASR_VAD_SILENCE_DURATION_MS` optional
  Milliseconds of silence required before Doubao closes a speech turn.

## Notes

- This resource is intended to be materialized into local config and executed locally.
- Configuration guidance for users should be derived from the env list above.
- The script follows Doubao Realtime events such as `transcription_session.update`,
  `conversation.item.input_audio_transcription.result`, and
  `conversation.item.input_audio_transcription.completed`.
