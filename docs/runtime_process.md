# runtime_process

- Source: `dust-runtime/src/runtime_process.ds`
- Forge: `Process`

## Constants

| Name | Type | Value |
|---|---|---|
| `MAX_TASKS` | `UInt32` | `256` |
| `INIT_PID` | `UInt32` | `1` |
| `ERR_DOMAIN_NOT_AVAILABLE` | `UInt32` | `100` |

## Procedures

### `proc K::process_init() -> UInt32`

- Emits `process_init`
- Returns `0`

### `proc K::init() -> UInt32`

- Wrapper for `process_init()`

### `proc K::spawn(entry: UInt64, stack_size: UInt32) -> UInt32`

- Returns `0` when `entry == 0`
- Returns `INIT_PID + 1` otherwise

### `proc K::join(pid: UInt32) -> UInt32`

- Returns `1` when `pid == 0`
- Returns `0` otherwise

### `proc K::exit(code: UInt32) -> UInt32`

- Returns `code`

### `proc K::yield() -> UInt32`

- Returns `0`

### `proc K::sleep(ms: UInt32) -> UInt32`

- Returns `0`

### `proc K::getpid() -> UInt32`

- Returns `INIT_PID`

### `proc K::get_task_count() -> UInt32`

- Returns `1`
