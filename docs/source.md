# UNDERWORLD

### Source Design Document (source.md)

---

# 1. Project Overview

## Project Name

**UNDERWORLD**

## Genre

Terminal-Based Sandbox Simulation / Crime RPG / Management Game

## Platform

* Terminal (CLI)
* Single Player
* Offline
* Persistent Save System

---

# 2. Vision

UNDERWORLD is a living, terminal-based sandbox where the player begins with nothing and gradually builds a life in a city that constantly reacts to every decision.

The game is **not mission-driven**.

Instead, it is **system-driven**.

Every action influences another system.

The player creates their own story through choices rather than following scripted missions.

---

# 3. Core Philosophy

The player should never ask:

> "What am I supposed to do?"

Instead they should ask:

> "What should I do next?"

The game emphasizes:

* Freedom
* Simulation
* Consequences
* Emergent Gameplay
* Long-term Progression

There is no single "correct" way to play.

---

# 4. Design Pillars

## Living World

The city continues existing whether the player interacts with it or not.

NPCs work.

Businesses earn money.

Police patrol.

Prices fluctuate.

Weather changes.

Events happen.

---

## Player Freedom

The player chooses their own life.

Possible paths include:

* Street Thief
* Crime Boss
* Pawn Shop Owner
* Taxi Company Owner
* Casino Owner
* Business Tycoon
* Real Estate Investor
* Completely Legitimate Citizen

Crime is one path—not the only path.

---

## Consequences

Every decision has effects.

Example:

Steal many cars

↓

Police increase patrols

↓

Insurance becomes expensive

↓

Pawn shops offer lower prices

↓

Vehicle theft becomes harder

Nothing exists in isolation.

---

## Progression

Every hour played should unlock larger opportunities.

Small risks become large operations.

---

# 5. Gameplay Loop

```
Explore

↓

Find Opportunity

↓

Take Risk

↓

Earn Money

↓

Upgrade

↓

Unlock Bigger Opportunities

↓

City Reacts

↓

Repeat
```

---

# 6. World

The city is divided into districts.

Each district has unique businesses, dangers, economy and opportunities.

---

## North District

* Luxury Area
* High-end Car Dealership
* Casino
* Bank
* Wealthy Citizens

Higher rewards.

Higher police presence.

---

## South District

* Apartments
* Cheap Cars
* Pawn Shop
* Convenience Stores
* Small Businesses

Ideal starting area.

---

## Industrial District

* Warehouses
* Factories
* Garages
* Scrap Yards
* Chop Shops

Vehicle-focused activities.

---

## Harbor

* Shipping Containers
* Smuggling
* Docks
* Cargo

Late-game opportunities.

---

## Downtown

* Police HQ
* Hotels
* Mall
* Nightclubs
* Government Buildings

Highest security.

---

# 7. Time System

The world operates on time.

Possible implementation:

Morning

Afternoon

Evening

Night

or

24-hour clock.

Time affects:

* Business hours
* NPC schedules
* Crime difficulty
* Police activity
* Available events

---

# 8. Weather

Possible weather:

* Sunny
* Rain
* Fog
* Storm

Weather should affect gameplay.

Examples:

Rain:

* Fewer pedestrians

Fog:

* Easier escapes

Storm:

* Lower visibility

---

# 9. Player

The player begins with almost nothing.

Starting conditions:

* Very little money
* Tiny apartment
* No respect
* No connections
* Basic inventory

The player grows naturally.

---

# 10. Player Statistics

Core stats:

* Money
* Health
* Energy
* Hunger
* Heat (Wanted Level)
* Respect
* Reputation
* Luck
* Stress
* Housing
* Transportation

Each stat influences gameplay.

---

# 11. Inventory

Inventory can contain:

Cash

Weapons

Phone

Keys

Fake IDs

Tools

Food

Medicine

Vehicle Keys

Illegal Goods

Inventory expands over time.

---

# 12. Vehicles

Every vehicle has its own properties.

Possible attributes:

* Condition
* Fuel
* Speed
* Storage Capacity
* Owner
* VIN
* Police Flag
* Insurance
* Value

Vehicle states:

* Owned
* Borrowed
* Stolen
* Destroyed

---

# 13. Economy

The economy is dynamic.

Items include:

* Food
* Gas
* Jewelry
* Electronics
* Cars
* Weapons
* Gold
* Phones
* Illegal Goods

Prices should fluctuate naturally.

Supply and demand should matter.

---

# 14. Businesses

Businesses available to own later:

* Pawn Shop
* Garage
* Casino
* Bar
* Nightclub
* Taxi Company
* Restaurant
* Car Wash
* Warehouse
* Construction Company

Businesses become sources of long-term income.

Legal businesses can also hide illegal operations.

---

# 15. NPC System

NPCs should feel alive.

Types include:

* Citizens
* Police
* Mechanics
* Pawn Shop Owners
* Gang Members
* Dealers
* Taxi Drivers
* Lawyers
* Doctors
* Detectives
* Journalists

---

## NPC Data

Each NPC may have:

Name

Age

Occupation

Money

Mood

Fear

Relationship

Trust

Memory

Daily Schedule

Location

---

# 16. Relationship System

NPCs remember interactions.

Example:

Pawn Owner

Trust:
82%

Last Interaction:
Bought stolen Mustang

Relationship:
Friendly

Result:

* Better prices
* New dialogue
* Discounts
* Special opportunities

---

# 17. Crime System

Possible crimes:

* Pickpocket
* Shoplifting
* Vehicle Theft
* Burglary
* Robbery
* Fraud
* Illegal Racing
* Money Laundering
* Weapon Smuggling
* Kidnapping

Every crime affects Heat differently.

---

# 18. Police System

Heat Levels

Heat 0

Nobody notices.

---

Heat 1

Occasional patrols.

---

Heat 2

Police actively search.

---

Heat 3

Roadblocks.

---

Heat 4

Detectives investigate.

---

Heat 5

City-wide manhunt.

Heat should decrease naturally if the player avoids attracting attention.

---

# 19. Random World Events

Examples:

* Police Strike
* Gang War
* Gas Price Increase
* Market Crash
* Festival
* Power Outage
* Casino Tournament

Events change the city temporarily.

---

# 20. Progression

The player may naturally evolve through stages.

Possible progression:

Nobody

↓

Street Thief

↓

Crew Member

↓

Gang Leader

↓

Business Owner

↓

Crime Boss

↓

City Legend

The game does not force this progression.

---

# 21. Save System

Persistent save.

Autosave after each day.

Player progress is permanent.

The world continues evolving over time.

---

# 22. Endgame

There is no mandatory ending.

Possible long-term goals:

* Become richest citizen
* Control every district
* Own every business
* Become legitimate
* Become a feared crime boss
* Survive for decades

The player decides what success means.

---

# 23. User Interface

Example layout:

```
╔════════════════════════════════════╗
║           UNDERWORLD              ║
╠════════════════════════════════════╣
║ Day        24                     ║
║ Time       21:43                  ║
║ Cash       $14,820                ║
║ Health     ████████░░ 80%         ║
║ Energy     ██████░░░░ 60%         ║
║ Heat       ★★☆☆☆                 ║
║ Respect    Local Criminal         ║
╚════════════════════════════════════╝

Location:
South District

Nearby:
🚗 Sedan
🏪 Pawn Shop
🚓 Police Cruiser
🚶 Tourist

Actions:

[1] Walk
[2] Interact
[3] Inventory
[4] Travel
[5] Phone
[6] Sleep
```

The interface should remain clean, readable, and immersive despite being terminal-only.

---

# 24. Core Design Goal

UNDERWORLD should not feel like "GTA in a terminal."

Instead, it should feel like a **living city simulation** that happens to be played entirely through the terminal.

The focus is not graphics.

The focus is making the player believe the city is alive.

---

# 25. Development Principle

Before adding new content, every new feature should answer:

* Does this make the world feel more alive?
* Does this create meaningful player choices?
* Does this interact with existing systems?
* Does it strengthen the core gameplay loop?

If the answer is **no**, the feature should be reconsidered.

---

# 26. Current Status

**Planning Phase**

No implementation decisions have been finalized.

This document defines the game's current design vision and serves as the foundation for future development.
