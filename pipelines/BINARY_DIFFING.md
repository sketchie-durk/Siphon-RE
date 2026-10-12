# Pipeline: Version Differential Analysis (Binary Diffing)

This pipeline is used to isolate changes between two versions of a binary, specifically to identify security patches.

## Workflow Steps
1. **Alignment**:
   - Using the Siphon-DB to identify common functions in both versions.
   - Aligning the CFGs of the two binaries to find matched blocks.

2. **Delta Isolation**:
   - Identifying "Modified" blocks where the CFG structure has changed.
   - Identifying "New" blocks added in the updated version.

3. **Patch Synthesis**:
   - Analyzing the delta to find the "Fix". (e.g., "Added a length check before a memcpy").
   - Reversing the fix to find the original vulnerability (The "1-Day" approach).

4. **Primitive Mapping**:
   - Mapping the discovered fix to a known primitive in the Grimoire (e.g., `[Buffer-Overflow]`).

## Tool Integration
- **Diffing**: BinDiff / Diaphora.
- **Verification**: Applying the discovered "Bug" to the older version to confirm the vulnerability.
