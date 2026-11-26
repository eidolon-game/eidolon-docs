# The First Descent | Abyss floor 1 production layout

Implementation brief for `abyss_001` in chapter 2. The existing authored grid is the spatial baseline. The metrics below specify how to turn that grid into a walkable Unreal map. Encounter, event and collision checks are pending an engine build. [Canon, chapter 2](../../narrative/story.md#capitolo-2--la-prima-discesa) · [Game layout and contract](https://github.com/eidolon-game/eidolon-game/tree/82c869f35e384c2b1462274e45612f928ea9e57e/Source/Eidolon/Dungeons/Data) · [Screenplay event contract](https://github.com/eidolon-game/eidolon-docs/pull/19)

## Route and module dimensions

Build 52 walkable cells from `abyss_001_authored.json`, each 200 × 200 cm. Use local Z up, floor surface Z = 0 and 300 cm clear height. The cell centre is `(200x + 100, 200y + 100, 0)`; World assigns one transform for the entire floor and its anchors. All coordinates below refer to the floor surface. Use a collision sweep to spawn the player capsule above the surface. The current pawn has a radius of 42 cm and half-height of 96 cm.

| Area | Metric footprint | Player experience |
| --- | --- | --- |
| Entry and checkpoint | Cells x 0–2, y 2–3. Entry (100, 500), checkpoint (500, 500). | Leave the Valdris approach behind. A broad landing gives space to read the movement prompt and turn without snagging. |
| Approach | x 3–4, y 2. | One straight, 400 cm corridor. A slot of light from the arena indicates the route. |
| Tutorial arena | x 5–9, y 0–5. Spawn anchors (1500, 500) and (1700, 700). | A 1000 × 1200 cm chamber teaches one foe at a time. Keep the central lane clear between approach, first spawn and gate. Keep a walkable loop around the second anchor for dodging. Place optional piers at the perimeter only. |
| Optional alcove | x 6–7, y 6. Centre anchor (1300, 1300). | Recess visible from the arena. The side detour has no mandatory objective or exclusive progression item. |
| Combat gate | Crossing from (9, 2) into (10, 2), gate plane X = 2000, centre Y = 500. | An operable door with its own collision. Closed state blocks the whole aperture. Open state leaves at least 150 cm clear width and 240 cm clear height. |
| Anomaly chamber | x 11–13, y 1–3. Anchor (2500, 500). | Movement and the exit silhouette remain legible through the effect. Convey the deformation and unclear voice through captioned sound and a reduced-motion alternative. |
| Exit passage | x 14–15, y 2. Exit (3100, 500). | Interact with a marked exit to return to the surface approach at `valdris_abyss`. This is a validated level transition. |

Use 200 × 200 × 18 cm floor pieces with their top faces aligned. Use 400 × 50 × 300 cm walls on pairs of contiguous collinear boundary edges; use shorter matching 200 cm pieces for single edges and cap exposed corners. Keep wall collision, overhead closure and door jambs outside the specified clear passage. Keep exposed corridor clearance at least as large as the open gate aperture. Use continuous perimeter and overhead collision, with no climbable seam at the gate or imported visual mesh. The OBJ is a placement reference. Build the playable collision and gate separately, then rebuild nav data and verify both gate states in Unreal.

## Ordered encounter and transitions

1. Only committed `mq_02/guild_register` enables entrance from `valdris_abyss`. Successful arrival establishes `abyss_floor_1` and makes the floor checkpoint available.
2. The first crawler spawns at the first anchor. The second spawns after confirmed defeat of the first. Give both slots distinct stable identities scoped to the encounter. A failed spawn remains incomplete; retry the absent slot. Combat owns defeat evidence and Quest accepts exactly one completion after both required slots are defeated. Save commits that result before the gate opens. The proposed `FirstMonster` combat profile uses 190 cm reach; Combat validates it against actual navigation and telegraphs.
3. The anomaly starts only after the player reaches its anchor with the committed combat step. Completion of the effect establishes `first_anomaly` once; repeated entry, skipped presentation and reload must preserve the appropriate state. Keep the event's meaning and pacing consistent for regular and reduced-motion presentation.
4. Resolve the exit target and require committed `first_anomaly` before validating `surface_return`. Handle failed map travel as retryable. The surface spawn faces the route back to the Guild and must not overlap the entrance trigger. Guild return, dormitory and Noah's reveal remain surface scenes.

## Acceptance on the packaged build

| Check | Expected result |
| --- | --- |
| Grid and scale | Loaded modular bounds and collision agree with the 3200 × 1400 cm envelope and anchor transforms. A pawn at every anchor has floor contact, headroom and a clear escape route. |
| Walkability and camera | Keyboard and controller can walk each route in both directions, turn on the landing and dodge in the arena. Check camera retraction against corridor walls and door jambs. AI paths in the arena reach the player without crossing closed boundaries. |
| Gate and bypass | Sprint, jump, dodge, and approach along every jamb and wall seam with the gate closed. Anomaly and exit remain inaccessible. After the commit, passage has clear collision and remains open after reload. |
| Failure and retry | Suppress each crawler spawn independently, including the second after the first has fallen. The gate stays closed. A successful retry permits completion once. |
| Checkpoint | Defeat and reload before the encounter, between crawler defeats, after the combat commit, and after the anomaly. Rebuild the floor from the last committed state. Verify gate, enemies and prompts agree, and verify that replay grants no duplicate completion or reward. |
| Accessibility and transition | Complete in Italian and English with captions, reduced motion and audio disabled. Check that the direction cues and exit status remain readable. Attempt the exit early and simulate a failed return; then use the valid exit and confirm the surface location and next Guild step. |
| Optional branch | Complete the route without visiting the alcove, then revisit it before the exit. Neither route changes mandatory quest requirements. |

The original Tools generator reproduced the committed Game PR layout JSON and OBJ byte for byte. The OBJ has 840 vertices and 630 quads; SHA-256 is `4aa54284fe29f972428e9d332349a75f4cfbed8b84978950c504ece4b1fbd095`. This checks the source layout only. Record the map source SHA, package SHA, inputs, result and log for each runtime acceptance row. [Generator source](https://github.com/eidolon-game/eidolon-tools/blob/abbf2ec75125eb74250d5079a15d64dd3177d1f8/scripts/dungeons/first_descent.py)
