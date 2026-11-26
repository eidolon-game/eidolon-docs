# UI/UX and accessibility — department handoff
Status: design and uncompiled C++ presentation model; no functional UMG screens yet.
Game base: feature/campaign-foundation (fc9cf93c896f3338356fc584b72f773a3d281181), stacked PR #6. Docs base: develop. No shared files modified.

## Visual language
Obsidian #141619 panel, ivory #F2E8D5 text, muted brass #C8A76A focus, crimson #D66B70 health, sage #8EBB91 stamina, azure #82B9DD mana. Opaque backing for text, minimum 4.5:1 normal text and 3:1 large text/non-text controls; never encode status solely in hue. Use original geometric broken-wall emblem and wordmark as future asset, no third-party references embedded. Engine default font is temporary; final font licensing pending. 1920x1080 reference, 5% safe margin, 24px body/32px subtitle baseline, 100–200% text scaling with wrapping and scroll. No mandatory flashing, blur or motion; stable focus outline and icon plus label.

## Screen specification
| Stable screen ID | Content and default focus | Owner dependency |
|---|---|---|
| Title | Continue if valid save, New Game, Load, Settings, Credits, Quit (PC) | Save/Core |
| NewGame | Difficulty, accessibility, slot confirmation; no overwrite without explicit confirmation | Save/Combat |
| Load | Slot list, chapter, timestamp, corruption/error message | Save |
| Settings | Graphics, audio buses, input rebinding, subtitles, text size, contrast, reduced motion; Apply/Cancel; timed display revert | Core/Audio |
| HUD | Health/stamina/mana label and value, objective, prompts; unavailable data hidden, boss name and phases when supplied | Combat/Quest |
| Pause | Resume, Inventory, Equipment, Skills, Map, Journal, Memories, Companions, Settings, Save, Title | Core/Save |
| Inventory | Category, list, details, quantity, weight only if RPG supports it | RPG |
| Equipment | Slot list, compare stats, equip confirmation | RPG |
| Skills | Node list alternative to graph, prerequisites and cost, unlock confirmation | RPG |
| Map | Discovered regions only; zoom/pan, marker list alternative, floor | World |
| Journal | Active/completed objectives, track action; hidden future objectives | Quest |
| Dialogue | Speaker, subtitle, choice list; no timed choice unless design explicitly requires it | Narrative |
| Merchant | Buy/sell, quantity, total, confirmation and result | RPG |
| Crafting | Recipe, materials, availability, result | RPG |
| Memories | Separate remembered and current reality records; chapter-gated | Discrepancy |
| Companions | Known companions, available commands, relationship information only if exposed | AI |
| Tutorial | Contextual prompt, replayable help, dismissal | Quest/Core |
| Death | Retry checkpoint, load, title; failure feedback | Save/Combat |
| Ending | Available choices only, confirmation; no hidden ending spoilers | Narrative |
| Credits | Scroll, pause, exit | Production |
## Input and integration
Common UI activatable stack is target; model provides screen IDs and bounded history but is not a widget stack. Use semantic Confirm/Back/NextTab/PreviousTab and Enhanced Input action glyphs per active device and mapping. Focus selected or first enabled item on entry, restore previous focus on back; no hover-only actions. Pause input ownership must be coordinated with Core. Do not change campaign state from presentation capture. Game-side model reads controller pawn and campaign subsystem; mana absent until Combat supplies it. Current campaign text is FString; migrate source to localized FText/string tables with Narrative. Do not infer unlocks from UI state. Save and RPG APIs must return explicit result, UI waits for acknowledgment. UI settings struct is not persistence. No changes to Build.cs or uproject without Core agreement.
## Acceptance matrix (pending UE)
Keyboard and controller: enter/exit each screen, focus visible, disabled items skipped, back restores focus, no traps, hot swap input glyphs, remap conflict and restore defaults. Test 720p/1080p/4K and safe area; 200% text no clipped controls; contrast measured on final backgrounds; grayscale status recognition; subtitle speaker and sound cues; reduced motion. Validate empty inventory, unavailable mana, zero max resources, invalid save, failed purchase, unknown map, locked skill, unavailable ending. Run Eidolon.UI.Model automation after UE5.6 build. Verify no future story spoilers, including Noah before discovery and secret ending before eligibility.
## Resource register
No external assets imported. Palette and screen specifications authored for EIDOLON; all rights reserved. No final logo, font, icons or binary widgets created.
## Next integration gates
Core: UMG/Slate/CommonUI dependencies, viewport, input routing, settings persistence. Combat: resource/boss events. RPG: inventory/merchant/skill transaction API. Quest/Save: localized objectives, slot metadata, failures. Then implement widgets, run automation and device playtests; keep draft until verified.
