# 🪙 Coin Math 3D — Educational 3D Math Adventure Game

An interactive 3D educational game built in Unity where players explore an open world, collect coins, battle enemies, and solve math challenges to level up. Designed to make mathematics engaging and rewarding for learners through game-based mechanics.

> 🎓 Built as part of a university Software Engineering project (4CS020)

---

## 📋 Table of Contents

- [About the Project](#about-the-project)
- [Gameplay Overview](#gameplay-overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [How to Play](#how-to-play)
- [Levels](#levels)
- [Scripts Overview](#scripts-overview)
- [Technologies Used](#technologies-used)
- [Team](#team)

---

## About the Project

**Coin Math 3D** is a 3D serious game that integrates mathematics curriculum content into an immersive, adventure-style game world. Players navigate through multiple levels, interact with NPCs, answer math questions (MCQs), collect coins as rewards, and face enemies — all while building real mathematical skills.

The game is grounded in educational theory, incorporating:
- **Game-Based Learning** (Gee, 2003; Prensky) — learning through immersive problem-solving
- **Cognitive Load Theory** (Sweller, 1994) — difficulty progression to stay within learners' Zone of Proximal Development
- **Self-Determination Theory** (Ryan & Deci, 2000) — coin rewards and level-ups to sustain intrinsic motivation

---

## 🎮 Gameplay Overview

Players control a 3D character exploring a world filled with:
- **Math challenge zones** — trigger areas that launch MCQ quizzes
- **NPC interactions** — talk to characters who present math questions
- **Coin collection** — earn coins by answering correctly
- **Enemy encounters** — enemies with AI that chase and attack; defeat them to progress
- **Level progression** — complete missions to unlock the next level

---

## ✨ Features

- 🌍 **3D Open World** — third-person character controller with camera follow
- ❓ **Math MCQ System** — multiple-choice questions triggered by game world zones
- 🪙 **Coin Reward System** — earn, spend, and track coins across sessions
- 🤖 **Enemy AI** — NavMesh-based enemies that chase and attack the player
- 🧑 **NPC Dialogue System** — proximity-based NPC interactions with branching answers
- 🚗 **Vehicle System** — driveable vehicles (lorry, bus) with enter/exit mechanics
- 🏆 **Level Up Panels** — visual feedback on mission completion and coin totals
- 🎬 **Animations** — character idle, run, attack, and clap animations via Animator
- 🔊 **Audio System** — in-game audio feedback
- 🗺️ **Multi-Level Design** — 3 levels with distinct missions and increasing difficulty

---

## 📁 Project Structure

```
CoinMath3D/
│
├── Scripts/
│   ├── Player/
│   │   ├── PlayerController.cs         # Movement & camera
│   │   ├── PlayerMovementScript.cs     # Extended movement logic
│   │   ├── PlayerHealth.cs             # Health system
│   │   ├── PlayerCombat.cs             # Attack mechanics
│   │   ├── PlayerInteract.cs           # Interaction system
│   │   └── PlayerSpawner.cs            # Respawn logic
│   │
│   ├── NPC/
│   │   ├── NPCInteraction.cs           # Proximity dialogue + MCQ
│   │   ├── NPCInteractable.cs          # Interactable NPC base
│   │   ├── NPCMovement.cs              # NPC patrol/movement
│   │   ├── NPCMissionTrigger.cs        # Mission activation via NPC
│   │   └── NPCTrigger.cs               # Trigger zone for NPC
│   │
│   ├── Enemies/
│   │   └── EnemyAI.cs                  # NavMesh chase & attack AI
│   │
│   ├── Coins/
│   │   ├── CoinManager.cs              # Singleton coin counter + UI
│   │   ├── CoinTrigger.cs              # Coin pickup trigger
│   │   └── CoinCheckTrigger.cs         # Validate coin count for progression
│   │
│   ├── Quiz/
│   │   ├── AnswerManager.cs            # Keyboard input answer checking
│   │   ├── QuizTrigger.cs              # Zone-based quiz activation
│   │   ├── ShowQuizOnTrigger.cs        # UI show/hide for quiz
│   │   ├── PondMCQManager.cs           # Pond area quiz logic
│   │   ├── LorryMCQManager.cs          # Lorry area quiz logic
│   │   ├── WatermarkMCQManager.cs      # Watermark area quiz logic
│   │   └── Level3MCQManager1.cs        # Level 3 quiz logic
│   │
│   ├── Levels/
│   │   ├── Level1Start.cs              # Level 1 initialisation
│   │   ├── Level2CompletePanelController.cs
│   │   ├── Level3Mission1Manager.cs
│   │   ├── Level3Mission2Manager.cs
│   │   ├── Level3Mission3MCQManager.cs
│   │   └── LevelCompleteTrigger.cs     # Trigger on level finish
│   │
│   ├── Vehicles/
│   │   ├── VehicleController.cs        # Vehicle driving logic
│   │   ├── VehicleEnterTrigger.cs      # Enter/exit vehicle
│   │   ├── VehicleMover.cs             # Autonomous vehicle movement
│   │   ├── BusMovement.cs              # Bus path movement
│   │   └── LorryMovement.cs            # Lorry path movement
│   │
│   ├── UI/
│   │   ├── LevelUpPanelController.cs   # Show coins on level up
│   │   ├── TriggerPanelController.cs   # General UI panel trigger
│   │   ├── StartMenu.cs                # Main menu logic
│   │   └── StartMenuManager.cs         # Menu scene manager
│   │
│   └── Misc/
│       ├── CameraFollow.cs             # Third-person camera
│       ├── ThirdPersonCameraScript.cs  # Advanced camera controls
│       ├── ArrowFloat.cs               # Floating arrow indicator
│       ├── ArrowHideTrigger.cs         # Hide arrow on trigger
│       ├── DoorTrigger.cs              # Door open/close mechanic
│       ├── FirewallTrigger.cs          # Firewall obstacle logic
│       ├── RotateObject.cs             # Spinning collectibles
│       ├── WaterDisappear.cs           # Water mechanic
│       └── IdleRunPreview.cs           # Preview animations
│
└── Assets/
    ├── Animations/                     # FBX character animations
    ├── Prefabs/                        # Reusable GameObjects
    └── ...
```

---

## 🚀 Getting Started

### Prerequisites

- [Unity 2022.x or later](https://unity.com/download) (LTS recommended)
- Git

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/coin-math-3d.git

# Open Unity Hub → Add project → Select the cloned folder
```

Then open the project in Unity Editor and load the starting scene from `Assets/Scenes/`.

---

## 🕹️ How to Play

| Action | Key |
|--------|-----|
| Move | `W A S D` or Arrow Keys |
| Interact with NPC | Walk into trigger zone |
| Answer MCQ | Press `1`, `2`, `3`, or `4` |
| Enter Vehicle | Walk to vehicle trigger |
| Camera | Mouse movement |

---

## 🗺️ Levels

| Level | Theme | Key Mechanic |
|-------|-------|-------------|
| Level 1 | Introduction | Basic movement, first NPC interactions, coin collection |
| Level 2 | Challenge Zone | Vehicle travel, MCQ quizzes at landmark zones (Pond, Lorry) |
| Level 3 | Boss Area | Enemy AI encounters, multi-mission MCQ chains, game finish |

---

## 🛠️ Scripts Overview

| Script | Purpose |
|--------|---------|
| `PlayerController.cs` | Handles WASD movement and third-person camera offset |
| `CoinManager.cs` | Singleton managing global coin count with TextMeshPro UI |
| `EnemyAI.cs` | NavMeshAgent-based enemy with chase, attack, and death states |
| `NPCInteraction.cs` | Proximity trigger for NPC dialogue + MCQ button UI |
| `AnswerManager.cs` | Listens for keyboard input (1–4) and validates answers |
| `LevelUpPanelController.cs` | Displays total coins on mission/level completion |
| `VehicleController.cs` | Driveable vehicle with enter/exit and movement physics |
| `QuizTrigger.cs` | Activates MCQ panel when player enters a trigger zone |

---

## 💻 Technologies Used

- **Unity 2022 (LTS)** — Game Engine
- **C#** — Scripting language for all game logic
- **Unity NavMesh** — Enemy AI pathfinding
- **TextMeshPro (TMP)** — In-game UI text rendering
- **Unity Animator** — Character and NPC animation state machines
- **Unity Physics & Colliders** — Trigger zones, combat, and interactions
- **Unity UI (Canvas)** — MCQ panels, HUD, menus
- **FBX Animations** — Third-party character animation assets

---

## 👥 Team

| Student | ID |
|---------|----|
| W. Udara Nethmi | 2501573 |
| Partner | 2502330 |

---

## 📄 License

This project was developed for academic purposes as part of a university Software Engineering module (4CS020). Not for commercial use.
