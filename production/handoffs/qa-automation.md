# QA handoff — 2026-11-26

Status: partial, NO-GO. Game base feature/campaign-foundation (PR #6, stacked on #5 and #4); docs/tools develop. No shared files changed. Coordination paths production/coordination.md and production/handoffs/game-director.md returned 404; director must confirm integration ownership.

## Evidence
Live campaign JSON and canonical story compared in JS: 26 chapters, 10 acts, 4 ending IDs, 26 matching titles. Python validator and eight unit test cases authored in tools/qa; Python execution pending. Game adds Eidolon.QA.Campaign.Boundaries; UE compile/run pending. No physical level reachability or packaging verified.

## Coverage matrix
| ID | Scope | Status | Acceptance |
|---|---|---|---|
| QA-001 | Campaign data | Passed (JS count/title check only) | 26 IDs, 10 acts, four endings, canonical titles, valid dialogue |
| QA-002 | Topology | Implemented, not run | All mandatory nodes reachable; stateful gates separately explored |
| QA-003 | Campaign runtime | Implemented test, not compiled | All 26 chapters, 200 sequential floors, 4 endings, reject skips |
| QA-004 | Combat | Not run | Damage/stamina bounds, death, dodge, block, collision, boss transitions |
| QA-005 | AI | Not run | Navigation, companion recovery, no stuck mandatory NPC |
| QA-006 | Quest/dialogue | Not run | Every mandatory choice and objective reachable; no spoiler leakage |
| QA-007 | Inventory/economy | Partial test source | Overflow, duplicate transactions, rollback, insufficient funds |
| QA-008 | Save/discrepancy | Not run | Round-trip, corrupted save recovery, atomic revision, no lost progress |
| QA-009 | Controller/accessibility | Not run | All mandatory actions keyboard and gamepad, remap, subtitles, focus |
| QA-010 | Performance | Blocked | Provisional target 60 fps at declared PC profile; p95 frame <= 16.7 ms, report hardware |
| QA-011 | Packaging | Blocked | Win64 executable plus cooked content, clean machine launch and playtest |
| QA-012 | Full playthrough | Blocked | All 26 chapters, 200 physical floors, four endings, no blocker/critical defects |

## Risks and reproduction
- QA-R01 (high): PR #5 Windows probe exits successfully when UE absent; artifact upload ignores missing files. Reproduce on hosted Windows runner without engine; expected packaging status blocked, actual probe may be green. Build Engineering owns correction.
- QA-R02 (high, source inspection): campaign LoadCampaign only checks schema, chapter index and nonnegative objective count; malformed floor/XP/inventory/ending values can pass. Create save with schema 1, valid chapter and floor 101; expected rejection/recovery, source predicts acceptance. Runtime reproduction pending. Save owner to address.
- QA-R03 (medium, source inspection): campaign automation initializes GameInstance, which calls LoadCampaign on the default slot before NewCampaign. Tests should use isolated temporary save slots; no destructive save calls in new test. Save owner to expose test fixture.

## Reproduction
Tools: python -m unittest discover -s qa -v; python qa/campaign_checks.py <game>/Content/Eidolon/Data/campaign.json <docs>/narrative/story.md.
Engine: run Eidolon.QA.Campaign.Boundaries via UE 5.6 Automation after successful editor build. Record exact commit, toolchain, logs, counts and failures. Do not interpret structural validation as runtime proof.

## Release gate
Zero open blocker/critical issues; 100% mandatory campaign paths and four endings verified in packaged build; no save corruption; controller and accessibility checklist passed; platform-specific performance budgets approved and measured. Console certification requires authorized SDK and hardware. Thresholds provisional pending director approval. No release approved.
