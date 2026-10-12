# Pipeline: Proprietary Protocol Siphoning

This pipeline is designed to decompose opaque network protocols into a formal state-machine specification.

## Workflow Steps
1. **Traffic Vacuuming**:
   - Capturing raw pcap data during targeted application behavior.
   - Performing entropy analysis on payloads to identify encrypted vs. compressed vs. plain-text blocks.

2. **Frame Recovery**:
   - **Field Inference**: Identifying static headers, length fields, and sequence numbers through multi-packet alignment.
   - **Delimiter Synthesis**: Detecting frame boundaries using frequency analysis of byte patterns.

3. **State Machine Inference**:
   - Mapping the sequence of packet types to application states (e.g., `HANDSHAKE` -> `AUTH` -> `DATA_XFER`).
   - Identifying "State-Triggers": Specific bytes that cause the protocol to transition between states.

4. **Intent Synthesis**:
   - Translating the inferred state machine into a formal specification (e.g., a Protobuf or ASN.1 definition).

## Tool Integration
- **Capture**: Wireshark / tcpdump / Scapy.
- **Analysis**: Netzob / Wireshark Lua Dissectors.
- **Verification**: Custom fuzzer to test the inferred state transitions.
