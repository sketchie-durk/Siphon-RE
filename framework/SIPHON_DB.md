# Framework: The Siphon-DB (Pattern Library)

The Siphon-DB is a centralized, evolving knowledge base of binary "fingerprints" and behavioral idioms.

## 1. The Fingerprint Model
Instead of simple hashes, Siphon-DB stores **Structural Fingerprints**:
- **CFG-Hashes**: Hashes of the control-flow graph of a function, invariant to register allocation.
- **Constant-Sets**: Sets of unique constants (e.g., S-Boxes in AES) that identify specific algorithms.
- **API-Call-Sequences**: Recurring patterns of system calls that signal a specific behavior (e.g., `OpenProcess` -> `VirtualAllocEx` -> `WriteProcessMemory` -> `CreateRemoteThread` = Process Injection).

## 2. Collaborative Synthesis
When **The Linguist** identifies a new semantic pattern, the agent proposes a new entry for the Siphon-DB.
1. **Pattern Extraction**: Isolating the minimal structural set that defines the behavior.
2. **Generalization**: Testing the pattern against different binaries to ensure it is not implementation-specific.
3. **Indexing**: Adding the pattern to the DB for future "Zero-Shot" recognition.

## 3. Integration
The Siphon-DB allows the Hive to perform **Instant Triage**. The Scout can scan a binary and immediately label 40% of the functions based on DB matches, allowing the Cartographer and Oracle to focus on the remaining 60% of "Unknown" logic.
