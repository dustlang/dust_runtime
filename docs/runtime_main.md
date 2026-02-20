# runtime_main

- Source: `dust-runtime/src/runtime_main.ds`
- Forge: `Runtime`

## Constants

| Name | Type | Value |
|---|---|---|
| `VERSION_MAJOR` | `UInt8` | `0` |
| `VERSION_MINOR` | `UInt8` | `3` |
| `ERR_OK` | `UInt32` | `0` |
| `ERR_DOMAIN_NOT_AVAILABLE` | `UInt32` | `100` |

## Procedures

### `proc K::runtime_init() -> UInt32`

Behavior:

- Emits `dust_runtime init`
- Calls:
  - `console_init()`
  - `memory_init()`
  - `interrupts_init()`
  - `process_init()`
- Returns `ERR_OK`

### `proc K::runtime_main() -> UInt32`

Behavior:

- Calls `runtime_init()`
- If init returns `ERR_OK`, emits `dust_runtime online` and returns `ERR_OK`
- Otherwise returns `1`

### `proc K::init() -> UInt32`

- Wrapper for `runtime_init()`

### `proc K::main() -> UInt32`

- Wrapper for `runtime_main()`

### `proc K::panic(msg: UInt64) -> UInt32`

Behavior:

- Emits `dust_runtime panic`
- Prints `msg` then newline
- Returns `1`
