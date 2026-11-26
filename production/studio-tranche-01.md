# Studio tranche 01

The release target remains the complete UE 5.6 single-player campaign with Italian and English, all 26 chapters, both 100-floor dungeons and four endings. The first owner-facing delivery is a packaged Win64 executable with its cooked content and dependencies. Windows players need no Unreal Editor. Console builds are deferred until platform authorization and development kits are available.

Use internally produced assets and verified free resources compatible with commercial redistribution. Keep provenance for every adopted asset. The current prototype outputs are candidates for M2 production review.

| Department | Reviewed result and next dependency |
| --- | --- |
| 01 Core | Candidate Game #25 fix gates progression on missing enemy spawns. Verify retry and chapter/floor transitions in Unreal. |
| 02 Combat | Candidate Game #26 fix aligns reach and checks contact at impact. Validate boss and player boundaries, line of sight and height. |
| 03 RPG | Game #10 and Tools #2 portable fixtures pass. Preserve legacy XP and require atomic quest reward receipts before activation. |
| 04 NPC | Game #9 standalone Legacy and M2 suites pass. First activation should use the tutorial monster and shared combat range/LOS. |
| 05 UI | Live HUD mixes languages. Use stable localized text keys, readable dialogue and IT/EN packaging before M2 acceptance. |
| 06 Save | Candidate #27 preserves memory on reload failure. Guard occupied or unreadable save slots at startup before schema migration. |
| 07 Story | Adopt the ordered chapter 2 reveal after the dormitory. The current runtime introduces Noah in chapter 3. |
| 08 Quest | Game #23 requires a trusted active-target validator and atomic persisted cursor before it can satisfy #28. |
| 09 Lore | Gate knowledge on the committed reveal rather than the chapter number, with reload checks. |
| 10 Character | Reproduced Noah's reference vest GLB and checksum. Child model, rig and visual review are pending. |
| 11 Creatures | Reproduced the Titan graybox and validated 46 registry records. Start the chapter 2 crawler as a separate asset. |
| 12 Environment | Select a small stone, Guild dormitory and catacomb module batch. Verify pivots, collision and lighting on import. |
| 13 Equipment | Validated 81 records and three graybox meshes. Produce a cosmetic starting sword before introducing stat-bearing equipment. |
| 14 Cinematics | Exporter reproduces seven transform clips. Noah reveal still needs skinned rigs, scene anchors, subtitles and skip recovery. |
| 15 Audio | Reproduced 13 source-original WAVs with matching SHA-256. Check loops, mix and state-driven playback in UE. |
| 16 World | Four Tools #9 tests pass. Connect Valdris POIs by walkable routes and gate access on the ordered quest state. |
| 17 Dungeons | Validated 200 prototype graph records and IDs. Five topologies repeat, so prototype coverage does not satisfy the 200 authored floors gate. Import and play abyss_001 first. |
| 18 Asset Pipeline | Calibration GLB round-trip passed. Local CPU preview required disabling denoising in a scratch copy because this Blender lacks OpenImageDenoise. UE import pending. |
| 19 Build | Game wrapper compiles, tests and packages on an authorized UE 5.6 Windows host. Workflow is manual and additionally needs registration on the default branch to dispatch through GitHub. |
| 20 QA | Source checks and portable tests executed. UE compile, automation, packaging, launch and manual regressions are pending. |

The first Win64 gate packages the Arena in Development configuration. M2 then validates the full ordered First Descent sequence, checkpoint recovery and IT/EN presentation. M5 requires the complete localized campaign, signed-off assets, performance and verified distribution. No engine build or executable has been produced by this tranche.

The Windows wrapper can run directly from a clean reviewed checkout on a licensed Windows build host with PowerShell 7, UE 5.6 and the project compiler/SDK. Set UE_ROOT to the engine installation and run `pwsh -NoProfile -File scripts/build/Invoke-StudioWin64.ps1 -EngineRoot "$env:UE_ROOT"`. GitHub dispatch also requires an isolated Windows runner restricted to trusted workflows. Do not run public PR jobs on it.
