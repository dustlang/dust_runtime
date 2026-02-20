# runtime_interrupts

- Source: `dust-runtime/src/runtime_interrupts.ds`
- Forge: `Interrupts`

## Constants

| Name | Type | Value |
|---|---|---|
| `IDT_SIZE` | `UInt32` | `256` |
| `IRQ_BASE` | `UInt32` | `32` |
| `ERR_DOMAIN_NOT_AVAILABLE` | `UInt32` | `100` |

## Procedures

### `proc K::interrupts_init() -> UInt32`

- Emits `interrupts_init`
- Returns `0`

### `proc K::init() -> UInt32`

- Wrapper for `interrupts_init()`

### `proc K::enable() -> UInt32`

- Emits `interrupts_enable`
- Returns `0`

### `proc K::disable() -> UInt32`

- Emits `interrupts_disable`
- Returns `0`

### `proc K::register_handler(vector: UInt32, handler: UInt64) -> UInt32`

- Returns `1` when `vector >= IDT_SIZE` or `handler == 0`
- Returns `0` otherwise

### `proc K::enable_irq(irq: UInt32) -> UInt32`

- Returns `register_handler(IRQ_BASE + irq, 1)`

### `proc K::disable_irq(irq: UInt32) -> UInt32`

- Returns `1` when `irq >= IDT_SIZE`
- Returns `0` otherwise

### `proc K::send_eoi() -> UInt32`

- Emits `interrupts_eoi`
- Returns `0`
