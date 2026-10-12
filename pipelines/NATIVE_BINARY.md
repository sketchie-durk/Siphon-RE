# Pipeline: Native Binary Decomposition

This pipeline is designed to take a stripped native binary and produce a high-level architectural map.

## Workflow Steps
1. **Initial Triage**: 
   - Entropy analysis to find packed/encrypted sections.
   - String extraction for clue-gathering.
   - Import/Export table analysis.

2. **Automated CFG Recovery**:
   - Use recursive descent to map all reachable functions.
   - Identify "Hub Functions" (functions with high in-degree/out-degree) as potential dispatchers.

3. **Semantic Labeling**:
   - Agentic analysis of function signatures.
   - Cross-referencing with known library hashes (FLIRT).

4. **Intent Synthesis**:
   - Grouping related functions into "Modules" (e.g., Networking, Encryption, File I/O).
   - Generating a high-level summary of the binary's purpose.

## Tool Integration
- **Static**: Ghidra / IDA Pro / Binary Ninja.
- **Dynamic**: x64dbg / GDB / Frida.
- **Verification**: Z3 / Angr.
