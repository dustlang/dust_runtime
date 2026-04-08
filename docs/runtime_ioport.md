# runtime_ioport

- Source: `dust-runtime/src/runtime_ioport.ds`
- Forge: `IoPort`

## Constants

| Name | Type | Value |
|---|---|---|
| `ERR_DOMAIN_NOT_AVAILABLE` | `UInt32` | `100` |

## Procedures

### `proc K::inb(port: UInt16) -> UInt8`

- Returns `0` when `port == 0`
- Returns `255` otherwise

### `proc K::outb(port: UInt16, value: UInt8) -> UInt32`

- Returns `1` when `port == 0`
- Returns `value` otherwise

### `proc K::inw(port: UInt16) -> UInt16`

- Returns `0` when `port == 0`
- Returns `65535` otherwise

### `proc K::outw(port: UInt16, value: UInt16) -> UInt32`

- Returns `1` when `port == 0`
- Returns `0` otherwise

### `proc K::inl(port: UInt16) -> UInt32`

- Returns `0` when `port == 0`
- Returns `4294967295` otherwise

### `proc K::outl(port: UInt16, value: UInt32) -> UInt32`

- Returns `1` when `port == 0`
- Returns `0` otherwise
