# DungeonOfCursed-reconstructed

Portfolio repository reconstructed from a Unity project.  
Focused on procedural dungeon generation and core gameplay systems.

## Overview

This repository is a reconstructed portfolio project based on a team-developed Unity game.  
Only the parts I contributed to have been extracted and reorganized.

The purpose of this repository is to showcase system design, algorithm implementation,  
and problem-solving processes rather than providing a complete gameplay experience.

## Key Systems

Dungeon of Cursed is a roguelike game where players explore procedurally generated dungeons.

To support random map generation, the system needed to ensure:

- All rooms are fully connected and traversable  

To achieve this, a BSP-based dungeon generation system was implemented.

- Space is recursively partitioned into a hierarchical structure  
- Rooms are generated within each partition  
- Connections are created to ensure all rooms are reachable  

A key challenge was guaranteeing connectivity under all partition layouts.  
To solve this, the system dynamically adjusts connection directions between nodes,  
ensuring that all rooms remain reachable regardless of how the space is partitioned.

## Sample Scope

This repository focuses on the core dungeon generation logic, including:

- BSP-based space partitioning  
- Room placement within partitions  
- Connection logic ensuring full traversal  

Non-essential gameplay elements are excluded to clearly highlight the core system.

## Code Overview

This repository centers around a single core script:

- **MapGenerator** — handles dungeon partitioning and connectivity control  

### MapGenerator (`MapGenerator.cs`)

Responsible for generating the dungeon layout using a BSP-based recursive partitioning approach.

- `DivideRect`  
  Recursively splits the dungeon space into smaller regions, forming a BSP tree structure  
  → Defines the overall layout and partition hierarchy of the dungeon  

- Direction Control (`hRev`, `vRev`)  
  Boolean flags that control the ordering of child nodes during partitioning  

  - `hRev` → affects horizontal splits  
  - `vRev` → affects vertical splits  

  These flags allow the system to adjust subtree orientation during recursion,  
  ensuring that representative leaf nodes remain consistently exposed for valid connections.

For a detailed explanation of the connectivity strategy and design rationale,  
please refer to the Technical Documentation.

- [BSP Dungeon Generation & Connectivity Control](docs/bsp-dungeon-generation-and-connectivity.md)

## System Demo

This build includes a playable prototype demonstrating core systems.

- Platform: Windows  
- Scope: Prototype-level implementation  

[Download (Windows Build)](https://github.com/javaCof/DungeonOfCursed-reconstructed/releases/tag/doc-v1.0)

## External Links

- **Technical Documentation**  
  [BSP Dungeon Generation & Connectivity Control](docs/bsp-dungeon-generation-and-connectivity.md)

## Notes for Reviewers

- This is a **system-focused portfolio repository**, not a complete game  
- The primary focus is on procedural generation and algorithm design  
- Non-essential gameplay systems are simplified to highlight the core logic  

## Contact

- Email: javacoffee0930@gmail.com