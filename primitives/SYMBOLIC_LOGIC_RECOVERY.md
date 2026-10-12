# Primitive: Symbolic Logic Recovery (SLR)

**Objective**: Transform a complex set of assembly-level branches into a simplified mathematical logic expression.

## Logic Flow
1. **Path Constraint Extraction**: Use symbolic execution (e.g., Angr) to identify the constraints required to reach a specific basic block.
2. **Constraint Simplification**: Pass the raw constraints to a SMT solver (Z3) to remove redundant conditions.
3. **Logic Synthesis**: Convert the simplified constraints into a high-level boolean expression (e.g., `(A > 10) AND (B == 0x41)`).
4. **Intent Mapping**: Map the boolean expression to a known logic pattern (e.g., "Range-based Access Control").

## Application
SLR is used by **The Oracle** to understand the exact conditions required to trigger a "hidden" function or a vulnerability, bypassing the need for manual trace analysis.
