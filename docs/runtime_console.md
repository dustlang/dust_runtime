# runtime_console

- Source: `dust-runtime/src/runtime_console.ds`
- Forge: `Console`

## Constants

| Name | Type | Value |
|---|---|---|
| `VGA_WIDTH` | `UInt32` | `80` |
| `VGA_HEIGHT` | `UInt32` | `25` |
| `COLOR_DEFAULT_FG` | `UInt8` | `15` |
| `COLOR_DEFAULT_BG` | `UInt8` | `0` |
| `ERR_OK` | `UInt32` | `0` |
| `ERR_DOMAIN_NOT_AVAILABLE` | `UInt32` | `100` |

## Procedures

### `proc K::console_init() -> UInt32`

- Calls `clear()`
- Calls `set_color(COLOR_DEFAULT_FG, COLOR_DEFAULT_BG)`
- Calls `set_cursor(0, 0)`
- Returns `ERR_OK`

### `proc K::init() -> UInt32`

- Wrapper for `console_init()`

### `proc K::putchar(ch: UInt8) -> UInt32`

- Emits `console_putchar`
- Returns `ch`

### `proc K::puts(ptr: UInt64) -> UInt32`

- Emits `console_puts`
- Returns `0` when `ptr == 0`
- Returns `1` otherwise

### `proc K::clear() -> UInt32`

- Emits `console_clear`
- Returns `ERR_OK`

### `proc K::set_cursor(row: UInt32, col: UInt32) -> UInt32`

- Returns `1` when `row >= VGA_HEIGHT` or `col >= VGA_WIDTH`
- Emits `console_set_cursor` and returns `ERR_OK` otherwise

### `proc K::get_cursor_row() -> UInt32`

- Returns `0`

### `proc K::get_cursor_col() -> UInt32`

- Returns `0`

### `proc K::set_color(fg: UInt8, bg: UInt8) -> UInt32`

- Emits `console_set_color`
- Returns `fg + bg`
