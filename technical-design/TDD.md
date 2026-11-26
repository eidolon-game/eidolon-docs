# Technical Design — draft

UE5 C++ core with Blueprint content. Start with a single runtime module; split only when dependency boundaries justify it. Proposed: Enhanced Input, GAS after combat spike, UMG/Common UI, StateTree or Behavior Trees, SaveGame, Primary Data Assets, Gameplay Tags. Discrepancies use stable entity IDs, versioned world-state changes and a memory ledger separate from current reality. No console SDKs in public Git. PC-first validation; console builds require platform approval and licensed tooling.

Pin UE5 minor version and compiler before first verified build. Define performance budgets after representative profiling.
