# adaptor.xifan.mtranserver-proxy

Managed local LLM adaptor that exposes MTranServer through an OpenAI-compatible API.

## Entry

- `entry.py`

## Runtime

- command: `python3`
- provides local endpoints compatible with:
  - `GET /v1/models`
  - `POST /v1/chat/completions`

## Environment Variables

- `MTRAN_URL` optional
- `MTRAN_TOKEN` optional
- `MTRAN_PORT` optional

## Notes

- This resource is intended to be materialized into local config and executed locally.
- Configuration guidance for users should be derived from the env list above.
