# Ownership
All paths are ownership proposals for integration, not claims that paths already exist. Shared legacy files require director coordination. Each department writes a handoff in its own branch under production/handoff/NN.md (docs), docs/handoff/NN.md (game/tools).
| ID | Owner | Preferred isolated paths |
|---|---|---|
|00|Director|production/, shared integration contracts|
|01|Core|Source/Eidolon/Core/; shared framework, input and module changes coordinated|
|02|Combat|Source/Eidolon/Combat/|
|03|RPG|Source/Eidolon/RPG/, Content/Eidolon/Data/RPG/|
|04|AI|Source/Eidolon/AI/, Data/AI/|
|05|UI|Source/Eidolon/UI/, Content/Eidolon/UI/|
|06|Save|Source/Eidolon/Save/, discrepancy state|
|07|Screenplay|narrative/screenplay/|
|08|Quest|Source/Eidolon/Quest/, narrative/quests/, Data/Quests/|
|09|Lore|narrative/lore/|
|10|Characters|art/characters/, Content/Eidolon/Characters/|
|11|Creatures|art/creatures/, Content/Eidolon/Creatures/|
|12|Environment|art/environment/, Content/Eidolon/Environment/|
|13|Equipment|art/equipment/, Content/Eidolon/Equipment/|
|14|Animation|art/animation/, Source/Eidolon/Animation/|
|15|Audio|art/audio/, Source/Eidolon/Audio/|
|16|World|Source/Eidolon/World/, world/regions/|
|17|Levels|Source/Eidolon/Dungeons/, world/dungeons/|
|18|Pipeline|tools asset generators, asset registry and import scripts|
|19|Build|.github/workflows/, packaging scripts|
|20|QA|tests/, QA reports, automation fixtures|
Legacy EidolonCharacter, EidolonGameMode, EidolonCampaignSubsystem, EidolonArenaEnemy, HUD, Build.cs, uproject, Config and shared schema: director coordinates edits with relevant owners. No force push or direct main writes.
