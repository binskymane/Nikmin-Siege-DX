# NIKMIN SIEGE DX DIRECTOR'S CUT: BATTLE

**A polished tower defense game featuring deployable Nikmin units and strategic tower defense gameplay**

## 🎮 Game Overview

Nikmin Siege DX is an enhanced tower defense game featuring:

- **Unique Nikmin Tower**: Deploy named colored minions (Red, Blue, Yellow) that autonomously attack enemies
- **5 Tower Types**: Pulse, Beam, Nova, Nikmin, and Heal towers with distinct strategies
- **Healing Tower**: AOE core healing at low levels, single-target Nikmin shielding at level 3+
- **Named Nikmin**: Each Nikmin gets a unique name from 60+ diverse global names
- **4 Upgrade Levels**: Enhance towers up to level 4 for maximum power
- **Endless Wave Mode**: Survive progressively harder enemy waves
- **Special Abilities**: EMP blast and Time Freeze for clutch moments
- **Polished Visuals**: Modern UI, particle effects, animations, and screen shake

## 🚀 Quick Start

**Option 1:** Double-click `index.html` in a modern web browser

**Option 2:** Serve locally (recommended):
```bash
python -m http.server 8000
# Then open http://localhost:8000/
```

## 🎯 How to Play

1. **Start**: Click "PRESS START" from the main menu
2. **Build**: Select a tower type from the left panel
3. **Place**: Click on empty grid cells (not on the path) to place towers
4. **Fight**: Press "START WAVE" to spawn enemies
5. **Upgrade**: Click placed towers to upgrade or sell them
6. **Deploy**: Nikmin towers spawn colored minions that hunt enemies
7. **Survive**: Use abilities strategically and survive all waves!

### Tower Types

- **🔺 Pulse Tower** (50 credits): Fast-firing, low damage - excellent for swarms
- **🟦 Beam Tower** (100 credits): Balanced damage and speed - reliable all-rounder
- **🔮 Nova Tower** (150 credits): Slow, devastating AOE damage - crowd control
- **🏠 Nikmin Tower** (125 credits): Deploys 3 types of named minions that attack enemies
  - 🔴 **Red Nikmin**: Fast speed, low damage
  - 🔵 **Blue Nikmin**: Balanced speed and damage
  - 🟡 **Yellow Nikmin**: Slow speed, high damage
- **✚ Heal Tower** (100 credits): Support tower with dual modes
  - **Level 1-2**: AOE mode - restores core health (must be in range of core)
  - **Level 3-4**: Laser mode - shields individual Nikmin with protective barriers

### Nikmin Mechanics

- Each Nikmin tower spawns colored minions in rotation (Red → Blue → Yellow)
- **Every Nikmin gets a unique name** from 60+ diverse global names (Carlos, Kenji, Omar, Lars, etc.)
- Minions autonomously find and attack the nearest enemy
- Minions die in one hit from enemy attacks (unless shielded by Heal tower)
- Max 6 minions per tower at level 1 (increases with upgrades)
- Each upgrade adds +2 max minions
- Minions provide consistent DPS without targeting limitations
- **Activity feed** shows individual Nikmin actions with their names and emojis (e.g., "🔴 Diego got kill #5")

### Special Abilities

- **⚡ EMP Blast** (100 credits, 15s cooldown): Deals 50 damage to ALL enemies
- **❄️ Time Freeze** (150 credits, 20s cooldown): Slows all enemies to 30% speed for 3 seconds

### Enemy Types

- **Nano-Bot** (Wave 1+): Basic enemy - 50 HP, 10 damage
- **Dart-Drone** (Wave 3+): Fast and weak - 30 HP, 5 damage
- **Siege-Core** (Wave 5+): Slow tank - 150 HP, 20 damage
- **Phase-Unit** (Wave 7+): Shielded - 80 HP + 50 shield, 10 damage
- **Omega-Titan** (Wave 10, 20, 30...): Boss - 500 HP, 30 damage

### Controls

- **Left Click**: Place tower / Select tower / Deploy minions
- **Right Click**: Cancel selection / Deselect
- **Space**: Start wave
- **Escape**: Pause / Resume game

## 🎨 Key Features

### Nikmin System
- 3 colored minion variants with unique stats
- Autonomous enemy hunting AI
- Visual feedback with colored particles
- Scales with tower upgrades
- Strategic minion type rotation

### Visual Polish
- Modern gradient UI with retro styling
- Particle systems for explosions, hits, and abilities
- Screen shake on impacts
- Animated glowing effects and bobbing minions
- Smooth transitions and hover states
- Colored minion indicators on Nikmin towers

### Game Mechanics
- Tower upgrades (4 levels per tower)
- Progressive difficulty scaling
- Boss waves every 10 rounds
- Strategic tower and minion placement
- Resource management
- Real-time targeting and pathfinding

### Quality of Life
- Placement preview with range indicator
- Tower selection with range visualization
- Real-time cooldown indicators on abilities
- Sell towers for 70% refund
- Wave completion bonuses
- Clear minion count and status

## 🏗️ Technical Architecture

### Core Systems

**Game Engine** (`src/game.js`)
- 60 FPS game loop with delta time
- State management for minions and towers
- Canvas rendering with camera shake
- Event handling

**Minion System** (`src/minion.js`)
- 3 minion types with unique stats
- Autonomous pathfinding to nearest enemy
- Attack mechanics with visual feedback
- One-hit death system
- Colored particle effects

**Grid System** (`src/grid.js`)
- 16×9 grid (960×540 canvas, 60px cells)
- Predefined enemy path with waypoints
- Tower placement validation
- Animated path visualization

**Enemy System** (`src/enemy.js`)
- 5 enemy types with unique behaviors
- Smooth path following
- Status effects (slow, burn)
- Health and shield systems
- Custom rendering for each type

**Tower System** (`src/tower.js`)
- 4 tower types with unique mechanics
- Nikmin tower spawns and manages minions
- Auto-targeting closest enemy in range
- Projectile system for standard towers
- 4-level upgrade system with scaling
- Visual feedback and animations

**Wave Manager** (`src/waves.js`)
- Dynamic wave generation
- Progressive difficulty
- Boss waves every 10 rounds
- Enemy composition variety

**Particle System** (`src/particles.js`)
- Burst effects for minion spawns
- Explosions with shockwaves
- Screen flashes for abilities
- Trail effects for projectiles

**UI Controller** (`src/ui.js`)
- Real-time HUD updates
- Button handlers
- Tower upgrade panel
- Ability cooldown displays
- Game over screen

## 📊 Game Balance

### Starting Resources
- Credits: 250 (increased for better early game)
- Core Health: 100

### Tower Stats & Costs

| Tower  | Cost | Damage    | Fire Rate | Range | Special         |
|--------|------|-----------|-----------|-------|-----------------|
| Pulse  | 50   | 15        | 1.0/s     | 120   | Fast firing     |
| Beam   | 100  | 40        | 0.67/s    | 150   | Balanced        |
| Nova   | 150  | 80 AOE    | 0.4/s     | 100   | Area damage     |
| Nikmin | 125  | Minions   | 3.0s      | 200   | Spawns minions  |

### Minion Stats

| Type   | Speed | Damage | Health | Attack Rate |
|--------|-------|--------|--------|-------------|
| Red    | 150   | 10     | 1      | 0.8s        |
| Blue   | 100   | 20     | 1      | 1.0s        |
| Yellow | 60    | 35     | 1      | 1.2s        |

### Upgrade Costs
- Level 2: Base cost × 80%
- Level 3: Base cost × 160%
- Level 4: Base cost × 240%

### Upgrade Benefits (per level)
- Damage: +50%
- Range: +20%
- Fire Rate: +15% faster
- Nikmin: +2 max minions per level

### Enemy Rewards
- Nano-Bot: 10 credits
- Dart-Drone: 15 credits
- Siege-Core: 25 credits
- Phase-Unit: 20 credits
- Omega-Titan: 100 credits

### Wave Bonuses
- Base: 20 credits + (wave × 5)

## 🎯 Strategy Guide

### Early Game (Waves 1-3)
- Start with 2-3 Pulse towers for basic coverage
- Save for a Nikmin tower by wave 2
- Deploy Nikmin near enemy path for constant damage
- Use credits from wave bonuses to expand

### Mid Game (Waves 4-7)
- Upgrade Pulse towers to level 2-3
- Add Beam towers for heavier enemies
- Upgrade Nikmin tower to spawn more minions
- Position towers to cover all path segments

### Late Game (Waves 8+)
- Add Nova towers for AOE against crowds
- Fully upgrade key towers to level 4
- Maintain 2+ Nikmin towers for minion swarms
- Save abilities for boss waves
- Strategic selling and rebuilding as needed

### Nikmin Tower Strategy
- Place early for consistent minion damage
- Upgrade for more minions (+2 per level, max 12 at level 4)
- Position centrally so minions can reach all enemies
- Complements slow-firing towers (Nova)
- Minions tank enemy focus away from towers

## 💻 Technical Details

- **Framework**: Vanilla JavaScript (ES6 modules)
- **Rendering**: Canvas 2D API
- **Resolution**: 960×540 (16:9 aspect ratio)
- **Target FPS**: 60
- **No build tools required**: Works in any modern browser

### Browser Compatibility
- Chrome/Edge 61+
- Firefox 60+
- Safari 11+

## 🔧 Development

### Project Structure
```
Nikmin-Siege-DX/
├── index.html          # Main HTML with game UI
├── styles.css          # Polished retro-themed CSS
├── src/
│   ├── main.js        # Entry point
│   ├── game.js        # Core game engine
│   ├── grid.js        # Grid and pathfinding
│   ├── enemy.js       # Enemy logic
│   ├── tower.js       # Tower and projectiles
│   ├── minion.js      # Nikmin minion system
│   ├── waves.js       # Wave management
│   ├── particles.js   # Particle effects
│   └── ui.js          # UI controller
└── README.md          # This file
```

### Design Philosophy

1. **Strategic Depth**: Nikmin towers add a new dimension to tower defense
2. **Visual Clarity**: Clear indicators for minions, cooldowns, and tower states
3. **Polish**: Smooth animations, particle effects, and satisfying feedback
4. **Balance**: 4 viable tower types with distinct strengths

## 📝 Features Highlights

✨ **New in Director's Cut:**
- 🏠 Nikmin Tower with 3 colored deployable minions
- 📈 4 upgrade levels per tower (up from 3)
- 🎨 Enhanced visual effects and minion animations
- 💰 Balanced economy with 250 starting credits
- 🎮 Improved tutorial hints and controls
- 🌟 Polished UI with Nikmin branding

---

**Deploy your Nikmin army and defend the core!** 🏠⚡🎮
