# CLAUDE.md

## Project overview

"Грабить Корованы" — a single-file browser-based 3D action RPG built with Three.js. The entire game (HTML, CSS, JS) lives in `index.html`.

## Architecture

- **Single file**: All code is in `index.html` (~1670 lines)
- **No build step**: Open `index.html` directly in browser
- **Three.js**: Loaded via CDN (`unpkg.com/three@0.160.0`)
- **Language**: Russian UI, English code

## Key systems (all in index.html)

- **Faction system** (line ~110+): 3 factions — elves, guards, villains. Determines enemy/ally relationships.
- **Combat** (~line 800+): Melee attacks, blocking, stamina management, damage calculation.
- **Injury/dismemberment** (~line 900+): Limb loss, eye injuries, bleeding, prosthetics.
- **Caravans** (~line 700+): 3 roaming caravans with guards, lootable for gold.
- **Shop** (~line 750+): Merchant NPCs sell weapons, potions, prosthetics.
- **NPC AI** (~line 600+): Patrol/chase/attack states, faction-based hostility, respawning.
- **World generation** (~line 400+): 4 zones, heightmap terrain, LOD trees, buildings.
- **Save/load** (~line 1000+): F5/F9, uses localStorage.
- **HUD** (~line 100+): Health/stamina bars, minimap, injury indicators.

## Conventions

- All game state is in global variables at the top of the script
- NPC behavior uses a simple state machine (patrol → chase → attack)
- Collision uses bounding-box push-out
- Gold is the single currency; earned from kills and caravan robbery

## Working with this project

- Since everything is one file, search by function name or comment section
- Test changes by refreshing the browser
- Save/load uses localStorage keys prefixed with game data
