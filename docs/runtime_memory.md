# runtime_memory

- Source: `dust-runtime/src/runtime_memory.ds`
- Forge: `Memory`

## Constants

| Name | Type | Value |
|---|---|---|
| `PAGE_SIZE` | `UInt32` | `4096` |
| `HEAP_START` | `UInt64` | `10485760` |
| `HEAP_END` | `UInt64` | `67108864` |
| `ERR_DOMAIN_NOT_AVAILABLE` | `UInt32` | `100` |

## Procedures

### `proc K::memory_init() -> UInt32`

- Emits `memory_init`
- Returns `0`

### `proc K::init() -> UInt32`

- Wrapper for `memory_init()`

### `proc K::alloc(size: UInt32) -> UInt64`

- Returns `0` when `size == 0`
- Computes `aligned = align_up(size, PAGE_SIZE)`
- Returns `0` when `aligned > HEAP_END - HEAP_START`
- Returns `HEAP_START + aligned` otherwise

### `proc K::free(ptr: UInt64) -> UInt32`

- Returns `1` when `ptr < HEAP_START` or `ptr > HEAP_END`
- Returns `0` otherwise

### `proc K::copy(dest: UInt64, src: UInt64, size: UInt32) -> UInt32`

- Returns `1` when `dest == 0` or `src == 0`
- Returns `size` otherwise

### `proc K::set(ptr: UInt64, value: UInt8, size: UInt32) -> UInt32`

- Returns `1` when `ptr == 0`
- Returns `size` otherwise

### `proc K::allocate_pages(count: UInt32) -> UInt64`

- Returns `alloc(count * PAGE_SIZE)`

### `proc K::free_pages(addr: UInt64, count: UInt32) -> UInt32`

- Calls `free(addr)`
- Returns `count` when free succeeds
- Returns free error code otherwise

### `proc K::align_up(size: UInt32, align: UInt32) -> UInt32`

- Returns `size` when `align == 0`
- Returns `align` when `size == 0`
- Returns `size + align` otherwise
