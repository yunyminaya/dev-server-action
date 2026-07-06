# LiveKit Dev Server Action

[![CI](https://github.com/livekit/dev-server-action/actions/workflows/ci.yml/badge.svg)](https://github.com/livekit/dev-server-action/actions/workflows/ci.yml)

Install and run a LiveKit server in development mode for end-to-end testing.

## Usage

```yaml
- uses: livekit/dev-server-action@v1
  with:
    github-token: ${{ github.token }}
    version: v1.13.3
```

## Inputs

| Name           | Required | Default  | Description                                                              |
| -------------- | -------- | -------- | ------------------------------------------------------------------------ |
| `github-token` | Yes      |          | Token used to download the LiveKit server release.                       |
| `config`       | No       | `""`     | Server configuration YAML                                                |
| `version`      | No       | `latest` | LiveKit server release to install. Accepts `latest`, `v1.13.3`, or `1.13.3`. |

`version` is supported on Linux and Windows release downloads. macOS uses the
Homebrew package and only supports the latest version.

## Outputs

| Name       | Description                       |
| ---------- | --------------------------------- |
| `pid`      | Process ID of the running server. |
| `log-path` | Path to the server log file.      |
