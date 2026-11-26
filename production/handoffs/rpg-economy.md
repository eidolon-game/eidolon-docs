# RPG & Economy handoff

Status: provisional implementation, not integrated or UE compiled. All rights reserved; original numerical design only.

## Ownership and integration
Game base feature/campaign-foundation (PR #6, stacked on #5/#4); docs and tools base develop. No shared source modified. Campaign subsystem remains the persistence authority. Its existing XP is linear, objective XP is 25 per applied count, rank A is floor-based and chapter 7 currently requires 100 additional giants after chapter 5. Coordinate migration before changing these behaviors. Do not instantiate a second persistent wallet. Existing int32 Gold and Inventory require a checked adapter or schema migration to int64. RankFacts must come from authoritative quest events; rank is never a substitute for sigil flags. Omega is the internal ID, Ω the localized display.

## Deliverables
Game: Content/Eidolon/Data/rpg/catalog.json and Source/Eidolon/Rpg/EidolonRpgRules.h. Tools: rpg/simulate.py and rpg/baseline.csv. Catalog is provisional, 63 items, 41 recipes, 30 skill nodes, 10 loot tables, 26 chapter budgets. Level cap 100; cumulative XP 50*(L-1)*(L+2); final XP 504900. Gold budget 79760, projected residual 35892 after essential spend. No empirical combat or economy playtest. The chapter budgets represent cumulative target deltas, not rewards to issue on top of individual encounters.

## API contract (portable)
Level(xp), Threshold(level), Rank(facts), Quantity(bag,id), Add, Buy, Sell, Craft, Reputation. Mutating transactions return bool; false must not change wallet. UI should read a snapshot, request an authoritative transaction, then refresh on success; never edit inventory or currency directly. Combat must consume a resolved stat snapshot, not infer damage from item price. Narrative supplies unique reward IDs and unlock flags; reward idempotency and persistent unique ownership history are outstanding. No engine adapter yet. Catalog ID strings are stable; localization keys should derive from IDs. Memory skills gated by eidolon_awakened (proposed flag, coordinate Narrative). Proposed unique relic is non-tradable and post-final only, not canon.

## Validation
Catalog generated and checked in JS for unique item IDs, recipe references, chapter XP totals and direct buy-craft-sell arbitrage. Baseline CSV generated from committed catalog. Python and C++ tests still require actual execution; no UE compilation or packaging performed. 

## Remaining gates
Runtime catalog loading/cooking, save migration, event idempotency, equipment instances and slots, durability/upgrades, actual attributes and skill effects, gathering respawn, merchant stock and region pricing, companion XP and autonomous progression, faction/city reputation, seeded loot, test coverage, UI/GAS/Combat bridges, actual 26-chapter playtest tuning. Coordinate chapter 2/4 floor handling, canonical giant counts, rank gates, memory flag, and director ownership. Do not merge until reviewed and tested.
