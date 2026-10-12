# Framework: The Intent Recovery Model

The core objective of Siphon-RE is the **Recovery of Intent**. Intent is the high-level goal of a block of code, stripped of its specific implementation details.

## 1. The Abstraction Hierarchy
Siphon-RE operates across four levels of abstraction:
1. **Machine Level**: Raw Opcode/Assembly.
2. **Structural Level**: Control-Flow Graphs (CFG) and Data-Flow Graphs (DFG).
3. **Semantic Level**: Mapping structures to known idioms (e.g., "Standard Library String Copy").
4. **Intent Level**: High-level purpose (e.g., "Encryption Round 1").

## 2. The Synthesis Engine
The engine uses a "Pattern-Match and Project" loop:
- **Match**: Identifying a structural pattern (e.g., a loop with a XOR operation).
- **Project**: Hypothesizing the intent (e.g., "This is a TEA cipher implementation").
- **Verify**: Testing the hypothesis by modifying the binary (patching) or monitoring the output.

## 3. Intent-Based Navigation
Instead of linear disassembly, the agent navigates the binary based on **Intent-Triggers**. For example, to find the "Login Logic," the agent searches for "String Comparison" primitives near "Network Receive" primitives.
