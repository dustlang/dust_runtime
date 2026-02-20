# dust-runtime Workspace

- Source: `dust-runtime/State.toml`

## Workspace Metadata

| Key | Value |
|---|---|
| `name` | `dust_runtime` |
| `version` | `0.2.0` |
| `description` | `Dust Runtime - OS services for bare-metal DPL` |

## Sector Configuration

| Key | Value |
|---|---|
| `name` | `dust_runtime` |
| `path` | `src` |

## Target Configuration

Target section: `[target.x64-pc-none]`

| Key | Value |
|---|---|
| `linker` | `ld` |
| `linker_flags` | `["-nostdlib", "-static"]` |
