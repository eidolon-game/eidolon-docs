# Technical Design — draft

UE5 C++ core with Blueprint content. Start with a single runtime module; split only when dependency boundaries justify it. Proposed: Enhanced Input, GAS after combat spike, UMG/Common UI, StateTree or Behavior Trees, SaveGame, Primary Data Assets, Gameplay Tags. Discrepancies use stable entity IDs, versioned world-state changes and a memory ledger separate from current reality. No console SDKs in public Git. PC-first validation; console builds require platform approval and licensed tooling.

Pin UE5 minor version and compiler before first verified build. Define performance budgets after representative profiling.

## Cycle 02 integration direction
UE 5.6 remains target. Runtime envelope separates sandbox/campaign, unique event identity and revision; trusted quest validation followed by atomic cursor/receipt/reward commit. ABI provisional pending 01/02/06/08 tests. Failed encounter spawn cannot unlock progress; failed checkpoint read must not reset state. CI standalone/structural/engine gates separate. Blender 4.5.0 calibration artifact verified at run 45861887309; UE import pending.
