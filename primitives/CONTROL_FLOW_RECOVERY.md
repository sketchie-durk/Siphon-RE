# Primitive: Control Flow Recovery (CFR)

**Objective**: Transform a linear sequence of instructions into a structured graph of logic.

## Logic Flow
1. **Basic Block Identification**: Identify boundaries where jumps or calls occur.
2. **Edge Mapping**: Resolve the targets of all jump instructions (conditional and unconditional).
3. **Graph Synthesis**: Construct the CFG.
4. **Pattern Recognition**: Identify common high-level constructs:
   - `IF-THEN-ELSE` -> Divergent paths merging at a single block.
   - `WHILE/FOR` -> Back-edges to a previous block.
   - `SWITCH` -> A single block jumping to multiple targets (jump table).

## Failure Modes
- **Indirect Jumps**: Jumps to registers (`jmp rax`) require dynamic analysis or symbolic execution to resolve.
- **Obfuscation**: Control-flow flattening or opaque predicates designed to break CFG recovery.
