# Primitive: Dynamic Taint Tracking (DTT)

**Objective**: Trace the flow of "Tainted" (user-controlled) data through the binary to identify reachable sinks.

## Logic Flow
1. **Source Identification**: Mark data from an external source (e.g., `recv`, `fread`) as Tainted.
2. **Propagation**: Use a DBI (Dynamic Binary Instrumentation) tool like Frida to track the Taint as it moves through registers and memory.
3. **Sink Detection**: Monitor for Tainted data reaching a critical function (e.g., `memcpy`, `system`, `strcpy`).
4. **Primitive Synthesis**: If Tainted data reaches a sink without proper validation, the primitive is labeled as a **Reachable Vulnerability**.

## Implementation Strategy
Siphon-RE implements DTT by hooking memory read/write operations and maintaining a shadow-memory map of taint-bits.
