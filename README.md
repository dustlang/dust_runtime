# Dust Runtime

OS services for bare-metal DPL kernels.

## Overview

Dust Runtime provides low-level OS services for DPL kernels running without libc:

- **Console I/O** - VGA text mode output
- **Memory Management** - Physical page allocation
- **Process Management** - Task scheduling
- **Interrupt Handling** - IDT and IRQ management
- **I/O Ports** - Direct hardware I/O

## DPL v0.2 Specification

This runtime implements the DPL v0.2 specification for bare-metal targets.

## Source Files

```
src/
├── runtime_console.ds    # Console I/O
├── runtime_memory.ds     # Memory management
├── runtime_process.ds   # Process/scheduler
├── runtime_interrupts.ds # Interrupt handling
├── runtime_ioport.ds    # I/O port operations
└── runtime_main.ds      # Main entry point
```

## Domain Support

| Domain | Status |
|--------|--------|
| K      | Full implementation |
| Q      | Stubbed |
| Φ      | Stubbed |

## Usage

```dust
K main {
    Runtime::K::main();
}
```

## Version

0.2.0
