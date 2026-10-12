# Agentic Orchestration: The Siphon-RE Hive

To achieve high-fidelity decomposition, Siphon-RE does not use a single agent, but a **Specialized Hive** of agents with distinct cognitive roles.

## 1. The Hive Roles
| Role | Cognitive Focus | Primary Toolset |
|---|---|---|
| **The Scout** | Surface mapping & Triage | `Strings`, `Entropy-Analysis`, `Import-Audit` |
| **The Cartographer** | Structural Recovery | `CFG-Synthesis`, `Cross-Reference-Mapping` |
| **The Linguist** | Semantic Translation | `Idiom-Recognition`, `Type-Inference` |
| **The Oracle** | Intent Synthesis | `Symbolic-Execution`, `Pattern-Projection` |
| **The Adversary** | Verification & Fuzzing | `AFL++`, `Z3-Solver`, `Differential-Analysis` |

## 2. The Orchestration Loop
1. **The Scout** identifies a high-interest area (e.g., a block with high entropy and frequent X-refs).
2. **The Cartographer** maps the precise control flow and data dependencies.
3. **The Linguist** translates the assembly patterns into semantic primitives.
4. **The Oracle** synthesizes the architectural intent.
5. **The Adversary** attempts to break the synthesized model via targeted fuzzing.
