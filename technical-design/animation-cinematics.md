# Animation and cinematic production contract

Status: specification, not imported, compiled, integrated or approved. All rights reserved. No third-party assets included.

## Runtime
Use in-place locomotion with movement-component authority; blend idle/walk/run/sprint by speed and direction, with start/stop/pivot states and airborne jump/fall/land. Proposed blend times 0.15–0.25 s, subject to playtest. Use montage root motion only for explicitly authorized committed moves; combat owns hit windows, damage and cancel eligibility. Animation notifies are presentation cues, never sole damage authority. Separate upper-body slots for compatible interactions. Death interrupts all cosmetic actions. IK foot placement traces ground and fades out airborne; pelvis offset clamped per rig. IK Retargeter uses authored reference poses and named chains; preserve child proportions, never scale adult Noah from Kael. Control Rig handles gaze, hands, feet and cinematic corrections. Facial tracks use localized dialogue timing, gaze and emotional beats; no automatic dialogue invented.

Titan traversal: movement owner supplies stable moving anchor ID, bone-local transform, revision and valid contact normal; animation resolves hand/foot IK against current anchor each frame, with detach on invalidation, death or streaming loss. No persistent save ownership. Creature profiles use species-specific chains and authored attack anticipation; giant movement cadence scales by anatomy rather than simply slowing human clips.

## Sequencer
Use 30 fps editorial timing (provisional), camera cut track, actor bindings by stable ID, transform/animation/facial/audio/subtitle tracks. Resolve required bindings before takeover. Skip and normal completion converge on one idempotent campaign-owned completion request; abort restores camera/input and does not advance. Save only through campaign subsystem. Do not play future-revision actors before committed world state. Dialogue IDs and scene IDs must be reconciled with screenplay; no fabricated lines. Camera shake and flashes must have reduced-motion alternatives. Preserve player equipment, companion presence and reality variant. No hard references to uncreated assets.

## Shot design: Noah arrival (chapter 2)
Proposed 18 s, 540 frames, after the first descent and overnight stay, on the return home. 0–119: 35 mm follow Kael to door, natural morning light. 120–209: 50 mm low interior reverse, Noah runs toward Kael. 210–329: 50 mm medium two-shot, child embraces Kael, Kael freezes; canonical address "fratellone". 330–449: 85 mm close-up Kael, confused gaze toward Elara. 450–539: 50 mm family reaction; Elara confirms Noah waited all night (dialogue timing pending screenplay). Restore camera to player; chapter completion only through campaign-authorized objective. Child contact targets authored on distinct rigs. No supernatural visual effect on Noah.

## Acceptance
Verify foot sliding, contact, interruption, montage recovery, weapon sockets, retargeting, child proportions, facial sync, camera collision, reduced motion, skip/replay and save/load around every cinematic; profile representative crowds and Titans. No final asset claim before engine import and visual review.

## Handoff
Base game campaign-foundation, docs/tools develop. Coordinate Combat (windows/root motion), Core (movement/input), Creature/Character (rig names and sockets), Screenplay (scene IDs and full dialogue), Save/Quest (completion and revision), Audio (localized cues), UI (skip/subtitles). Shared files untouched. Pending: actual rigs, authored clips, Sequencer assets, engine tests and approval.
