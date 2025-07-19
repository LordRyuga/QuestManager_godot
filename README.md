# QuestManager Plugin for Godot

**QuestManager** is a lightweight and modular Godot plugin to handle quests and objectives using `Resource`-based architecture.  
It is designed to be independent of your existing systems but can easily integrate with JSON-based save systems via extension.

---

## ✨ Features

- `QuestResource` to define quests
- `ObjectiveResource` for individual objectives
- `QuestManager` autoload to manage and track quest progress
- Clean, scalable, and extensible design
- Easily integratable into custom save systems

---

## 🛠️ Installation

1. Clone or download this repository into your project’s `addons/quest_manager` folder.
2. In Godot:
   - Go to **Project → Project Settings → Plugins**
   - Enable the plugin: `QuestManager`

3. Autoload `QuestManager`:
   - Go to **Project → Project Settings → Autoload**
   - Add a new entry:
     - **Name**: `QuestManager`
     - **Path**: `res://addons/quest_manager/quest_manager.gd`
     - Enable **Singleton**

---

## 📦 Folder Structure

```
addons/quest_manager/
├── plugin.gd
├── plugin.cfg
├── quest_manager.gd
├── Quest manager.tscn
└── resources/
    ├── quest_resource.gd
    └── objective_resource.gd
```
## 📄 How to Use

### 1. Create a New Quest
1. Right-click in the FileSystem and choose:
   - **New Resource → QuestResource**
2. Fill in fields:
   - `id`, `name`, `description`, `objectives`, etc.
3. Add `ObjectiveResource` entries to the `objectives` array.

### 2. Add Quests to Manager
1. First add the quest manager scene to autoload in project settings
2. Now add all the quests to it using the inspector.
3. call this function whenever needed in the game: QuestManager.update_quests("--objective-type--", "--target--"). For example when you kill a bandit, you call QuestManager.update_quests("kill", "bandit")

