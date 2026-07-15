# UNDERWORLD Project Structure

This project is organized around **game systems**, not file types. Each directory represents a distinct part of the game, making the codebase scalable, modular, and easy to navigate.

---

# Directory Structure

```text
underworld/
│
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
│
├── docs/
│   ├── source.md
│   ├── roadmap.md
│   ├── changelog.md
│   ├── gameplay.md
│   ├── world.md
│   ├── economy.md
│   ├── npc.md
│   ├── police.md
│   └── ui.md
│
├── saves/
│   ├── autosave.json
│   └── save_slots/
│
├── data/
│   ├── items.json
│   ├── vehicles.json
│   ├── businesses.json
│   ├── districts.json
│   ├── events.json
│   ├── npc_names.json
│   └── dialogue.json
│
├── assets/
│   ├── ascii/
│   ├── banners/
│   └── themes/
│
├── tests/
│
├── src/
│   │
│   ├── main.py
│   │
│   ├── core/
│   │   ├── engine.py
│   │   ├── game.py
│   │   ├── state.py
│   │   ├── save_manager.py
│   │   ├── config.py
│   │   ├── constants.py
│   │   └── logger.py
│   │
│   ├── ui/
│   │   ├── screen.py
│   │   ├── menu.py
│   │   ├── input_handler.py
│   │   ├── renderer.py
│   │   ├── panels.py
│   │   └── notifications.py
│   │
│   ├── world/
│   │   ├── city.py
│   │   ├── district.py
│   │   ├── location.py
│   │   ├── weather.py
│   │   ├── clock.py
│   │   └── events.py
│   │
│   ├── player/
│   │   ├── player.py
│   │   ├── inventory.py
│   │   ├── stats.py
│   │   ├── skills.py
│   │   ├── phone.py
│   │   └── housing.py
│   │
│   ├── npc/
│   │   ├── npc.py
│   │   ├── civilian.py
│   │   ├── police.py
│   │   ├── gangs.py
│   │   ├── businesses.py
│   │   ├── memory.py
│   │   └── schedules.py
│   │
│   ├── economy/
│   │   ├── market.py
│   │   ├── pricing.py
│   │   ├── transactions.py
│   │   └── businesses.py
│   │
│   ├── vehicles/
│   │   ├── vehicle.py
│   │   ├── garage.py
│   │   ├── dealership.py
│   │   └── theft.py
│   │
│   ├── crime/
│   │   ├── crimes.py
│   │   ├── heat.py
│   │   ├── evidence.py
│   │   ├── police_ai.py
│   │   └── jail.py
│   │
│   ├── interactions/
│   │   ├── dialogue.py
│   │   ├── trading.py
│   │   ├── pawn_shop.py
│   │   ├── robbery.py
│   │   └── encounters.py
│   │
│   ├── systems/
│   │   ├── progression.py
│   │   ├── achievements.py
│   │   ├── reputation.py
│   │   ├── random_events.py
│   │   └── missions.py
│   │
│   └── utils/
│       ├── colors.py
│       ├── formatting.py
│       ├── helpers.py
│       └── random_utils.py
│
└── run.py
```

---

# Folder Overview

## Root Directory

Contains the project's entry point, configuration files, dependency list, license, and documentation.

---

## `docs/`

Contains all planning and design documents.

**Purpose**

* Game Design Document (GDD)
* System documentation
* Development roadmap
* Changelog
* Design notes

This folder should contain **ideas**, not implementation.

---

## `saves/`

Stores player save files.

Example:

* Autosaves
* Manual save slots
* Backup saves

The game should never store save files inside `src/`.

---

## `data/`

Contains static game content.

Examples:

* Items
* Vehicles
* District definitions
* Business definitions
* NPC names
* Events
* Dialogue

Keeping content separate from code makes balancing and expansion much easier.

---

## `assets/`

Stores non-code resources.

Examples:

* ASCII art
* Splash screens
* Themes
* Terminal banners

---

## `tests/`

Contains unit and integration tests.

As the game grows, every major system should have corresponding tests.

---

# Source Code (`src/`)

All gameplay code lives here.

The codebase is divided into independent systems.

---

## `core/`

The heart of the game.

Responsible for:

* Starting the game
* Game loop
* Global game state
* Configuration
* Saving and loading
* Logging

This folder should remain small and should **not** contain gameplay logic.

---

## `ui/`

Everything related to the terminal interface.

Examples:

* Rendering
* Menus
* Input handling
* Notifications
* Status panels

Responsible only for presentation.

---

## `world/`

Represents the game world.

Responsible for:

* City
* Districts
* Locations
* Weather
* Time
* World events

Everything related to the environment belongs here.

---

## `player/`

Contains everything directly related to the player.

Examples:

* Player object
* Inventory
* Statistics
* Housing
* Skills
* Phone

---

## `npc/`

Handles all non-player characters.

Includes:

* Civilians
* Police
* Gang members
* Business owners
* NPC memory
* Daily schedules

NPC behavior should remain isolated from player logic.

---

## `economy/`

Controls the game's economy.

Examples:

* Market prices
* Buying and selling
* Business profits
* Transactions

Should be the single source of truth for money flow.

---

## `vehicles/`

Everything involving vehicles.

Examples:

* Vehicle objects
* Garages
* Dealerships
* Vehicle theft
* Ownership

---

## `crime/`

Responsible for all criminal mechanics.

Examples:

* Crimes
* Wanted level
* Police investigation
* Evidence
* Jail

This folder manages law enforcement interactions.

---

## `interactions/`

Handles direct interactions between the player and the world.

Examples:

* Dialogue
* Trading
* Pawn shop
* Robbery
* Random encounters

---

## `systems/`

Contains game-wide systems that don't belong to one specific module.

Examples:

* Progression
* Reputation
* Achievements
* Missions
* Random world events

Think of these as overarching mechanics.

---

## `utils/`

Small reusable utilities.

Examples:

* Text formatting
* Colors
* Helper functions
* Random utilities

Avoid placing gameplay logic here.

---

# Design Principles

## Organize by Feature

Files should be grouped by **what they do**, not by their type.

Good:

```text
player/
inventory.py
stats.py
housing.py
```

Avoid:

```text
utils/
player_utils.py

helpers/
inventory_helpers.py

misc/
stats_misc.py
```

---

## Keep Systems Independent

Each major game system should be as self-contained as possible.

For example:

* The vehicle system should not know how the economy works internally.
* The UI should not contain gameplay logic.
* The economy should not directly manipulate the player's inventory.

Instead, systems should communicate through clear interfaces.

---

## Data-Driven Design

Whenever possible, store game content inside the `data/` folder rather than hardcoding values into Python files.

Examples include:

* Item definitions
* Vehicle definitions
* NPC names
* District layouts
* Dialogue
* Events

This makes the game significantly easier to balance and expand.

---

## Single Responsibility

Every file should have one clear purpose.

If a file starts handling multiple unrelated systems, consider splitting it into smaller modules.

---

## Scalability Goal

This structure is designed to support:

* Hundreds of items
* Hundreds of vehicles
* Thousands of NPCs
* Multiple districts
* Expandable gameplay systems
* Long-term development without becoming difficult to maintain
