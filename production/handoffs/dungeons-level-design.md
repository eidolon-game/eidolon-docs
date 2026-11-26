# Dungeon level design handoff — department 17

Status: graph prototype only. Canon: narrative/story.md (develop). Game base: feature/campaign-foundation (#6); docs/tools base: develop. No shared files edited.

## Floor contract
200 stable IDs abyss.001–100 and eternity.001–100. Five graph templates: linear, fork, loop, hub, switchback. Directed edges are progression abstractions, not walkable geometry. The trial gates exit; secrets are optional. Family and mechanic keys are provisional, not asset or encounter references. Boss slots every tenth floor are proposed except canon-specific anchors. Checkpoints are conceptual; save ownership remains with department 06. No early revelation of the Guild's purpose.

Abyss canonical ten bands: catacombs, buried forest, lost mines, sunken kingdom, crystal lands, necropolis, infernal forges, inverted citadel, silent sanctuary, abyss heart. Eternity cycles seven canonical trial laws: time, memory, life, death, matter, will, destiny; this order is provisional. Duration target 6 min per regular floor and 12 per boss slot (22 hours across both towers, excluding retries).

## Manual authoring requirements
Abyss 1: tutorial and perceptual disturbance, return to surface; Noah reveal outside dungeon. 70: statue; 90: creature says Ricorda; 100: Guardian and externally sealed Guild door; return to surface before Aldren grants seal. Eternity 100: Empyrea threshold, chapter 24; entry to tower requires founder keys, chapter 23. These are anchors only, not authored maps.
Oblivion: alternate Valdris and Noah reunion; final arena phases: childhood home, Abyss 1, Vareth ruins, Valdris walls, Oblivion; Origin decision after Aurelion defeat. Four ending spaces must be selected by authoritative campaign state, never random. Giant arenas and Titan climb routes require creature dimensions, nav and anchor contracts. Secondary dungeons and ruins remain unimplemented.

## Validation and integration
JS initial generation checked count, unique IDs, edge endpoints, all nodes reachable, direct trial-to-exit edge, and rejected one empty-edge negative case. Python generator/validator committed but execution not verified in this session. No Unreal maps, build, navigation, runtime gate, combat, lighting, or accessibility tests. No binary assets. All rights reserved.
Dependencies: Director for base/ID review; Quest for objective mappings; Save for persistent floor completion and checkpoints; Combat/AI for encounter IDs; Environment/Pipeline for modular geometry, collision and streaming. No changes to campaign subsystem. Acceptance requires manual narrative maps, secondary spaces, geometry generation, reachable physical routes, encounter tuning and UE playtests. Do not merge before review.
