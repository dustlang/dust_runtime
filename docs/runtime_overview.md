# dust-runtime Overview

- Project path: `dust-runtime/`
- Manifest: `dust-runtime/State.toml`
- Runtime domain: K-domain focused bare-metal services

## Purpose

`dust-runtime` provides core OS/runtime services for Dust kernels:

- Console I/O bootstrap and control
- Memory helper operations
- Process/task helper operations
- Interrupt helper operations
- Port I/O helper operations
- Runtime lifecycle entrypoints

## Runtime Forge Inventory

| Forge | Source | Constants | Procedures |
|---|---|---:|---:|
| `Runtime` | `src/runtime_main.ds` | 4 | 5 |
| `DustRuntimeBridge` | `src/runtime_bridge.ds` | 1 | 2 |
| `Console` | `src/runtime_console.ds` | 6 | 9 |
| `Memory` | `src/runtime_memory.ds` | 4 | 9 |
| `Process` | `src/runtime_process.ds` | 3 | 9 |
| `Interrupts` | `src/runtime_interrupts.ds` | 3 | 8 |
| `IoPort` | `src/runtime_ioport.ds` | 1 | 6 |

## Integration Pattern

The runtime is linked by higher-level system components (for example `xdv-os`) through bridge and lifecycle entrypoints.

Primary lifecycle path:

1. `runtime_init()`
2. subsystem initializers (`console_init`, `memory_init`, `interrupts_init`, `process_init`)
3. `runtime_main()`
