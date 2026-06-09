# survivor-lite

A Vampire Survivors-style top-down wave survival game built with Godot 4.

Survive endless waves of enemies, collect equipment drops, and upgrade your character between waves.

## Requirements

- [Godot 4.3+](https://godotengine.org/download/)

## Running

Open the project in Godot and press **F5**, or run from the command line:

```bash
godot --path . scenes/game/game.tscn
```

## Controls

| Key | Action |
|-----|--------|
| WASD / Arrow Keys | Move |
| Space | Dash |
| B | Open inventory (Bags / Stats) |
| C | Open stats (Bags / Stats) |
| ESC | Close panel |

The **B** and **C** keys both open the same panel — B lands on the Bags tab, C lands on the Stats tab. Click either tab to switch while the panel is open.

## Project Structure

```
scenes/
  game/         # Root game scene
  entities/     # Player and enemy scenes
  ui/           # HUD, inventory panel, upgrade screen
scripts/
  managers/     # Autoloaded singletons (GameManager, EquipmentManager, ...)
  entities/     # Player and enemy logic
  ui/           # UI controllers
resources/
  equipment/    # EquipmentData resources
  enemies/      # EnemyData resources
  upgrades/     # UpgradeData resources
```
