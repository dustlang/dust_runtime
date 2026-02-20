# runtime_bridge

- Source: `dust-runtime/src/runtime_bridge.ds`
- Forge: `DustRuntimeBridge`

## Purpose

Bridge forge used by `xdv-os` integration checks and runtime handoff flow.

## Constants

| Name | Type | Value |
|---|---|---|
| `RUNTIME_VERSION` | `UInt32` | `2` |

## Procedures

### `proc K::init() -> UInt32`

Behavior:

- Emits `dust_runtime bridge online`
- Calls `runtime_init()`
- Returns `RUNTIME_VERSION + 1`

### `proc K::handoff() -> UInt32`

Behavior:

- Emits `dust_runtime handoff path ready`
- Returns `runtime_main()`
