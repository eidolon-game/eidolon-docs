# Audio Bible — v0.1
Status: proposed, not approved. All rights reserved. Canon: narrative/story.md (develop, blob 1472f5be51fcfff4c7020d14cc70ab1723ac8104).

## Identity
Intimate human acoustic core expands to continental and celestial scale. Kael motif D4 F4 E4 A4; Noah A4 C5 B4 E5, gentle felt piano, never a divine reveal. Main theme 80 BPM 4/4, D minor. Musical proposals are original sketches, not final recordings. Abyss descends in register; Stair reverses the contour. City and encounter identities are in audio-events.json. Vareth is separate from the seven cities. Silence is intentional, not a missing asset.

## Runtime contract
Events use stable IDs in catalog. minChapter is a minimum spoiler gate, not authorization: Quest/Save must explicitly confirm encounter, region, reality and ending before requesting a cue. Audio never determines gameplay state. Restore from authoritative snapshot on load, discard stale requests on reality revision. Priority 0–100; dialogue > telegraph > combat > ambience. Music layers exploration, tension, combat, boss; intensity 0–1, enter combat at .65, exit below .35 after 5 seconds. Crossfade 2s; boss override .5s; narrative transitions on bar boundary when Quartz integration exists. Prototype uses seconds only. MetaSound inputs proposed: Intensity(float), RealityBlend(float), SurfaceIndex(int), TriggerPlay(trigger). Never assume a graph exists.

## Mix and spatial
48kHz PCM masters, mono spatial SFX, stereo music and ambience beds; -1 dBTP master ceiling target, music -23 LUFS integrated target, dialogue -18 LUFS target (measure in production). Separate Music/SFX/Dialogue/Ambience/UI buses, user volume controls, dialogue ducking 6 dB with 80ms attack/400ms release. HRTF optional, stereo fallback. Giant/Titan multi-anchor emitters, distance attenuation and obstruction; critical telegraphs remain audible without subwoofer. Provisional concurrency: 32 spatial voices, 8 footsteps, 4 impacts per emitter; profile before final. Captions and directional indicators for essential cues, reduced anomaly intensity, no mandatory tinnitus or sudden loud spikes.

## Narrative spotting
Ch1 home/forge/city; 2 tutorial anomaly and Noah; 3 intimacy; 4 Guardian; 5 first Giant/open air; 6 diary; 7 outer wall; 8 seven cities; 9 Titan cycle; 10 Vareth loss; 11 sky fracture; 12 divine research; 13 archive; 14 historical revelation; 15 Heart; 16 Noah human truth; 17 faction split; 18 Nhalor; 19 forgotten return; 20 Oblivion; 21 alternate family; 22 Noah reunion; 23 Stair laws; 24 Empyrea/Origin; 25 siege; 26 Aurelion and chosen ending. Ending I cyclical, II empty chair (no Noah motif), III restrained Guild cadence, IV human duet. No ending playback before confirmed choice.

## Production gates
Catalog is specification only. Original synthesis prototype lives in tools; no final music, voices, MetaSound graphs or SoundWaves claimed. Record Foley, creature layers, actors (authorized), score stems and loop points; validate loudness, clicks, subtitles, streaming, scene transitions and platform performance. No third-party references imported. No voice cloning. Localized line IDs shared with Screenplay; record only approved scripts, use age-appropriate casting for Noah, separate younger/older performance.
