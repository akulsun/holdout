# Holdout – Zombie Survival Shooter

A top-down wave-based zombie survival shooter built with vanilla **HTML5 Canvas**, **JavaScript**, and **Web Audio API**. Survive against escalating hordes of the undead, earn points, buy heavier weapons, customize weapon upgrade trees, and climb the global online leaderboard.

---

## 🎮 Play Directly in Your Browser

- **Zero dependencies & no build step**: Open the website in any modern web browser (Chrome, Firefox, Edge, Safari, Brave) to play instantly.
- **Audio out of the box**: All sound effects (gunfire, reloads, impacts, zombie roars) are synthesized on the fly via the Web Audio API—no external audio files or assets needed.

---

## 🕹️ Controls

| Action | Control |
| :--- | :--- |
| **Move** | <kbd>W</kbd> <kbd>A</kbd> <kbd>S</kbd> <kbd>D</kbd> |
| **Aim & Shoot** | Mouse (Left Click to Fire) |
| **Reload** | <kbd>R</kbd> |
| **Switch Weapon** | <kbd>1</kbd> – <kbd>5</kbd> or Mouse Scroll Wheel |
| **Armory & Upgrades** | <kbd>B</kbd> or the on-screen **⚡ Upgrades** button |
| **Skip Intermission** | <kbd>Enter</kbd> (starts next wave immediately) |
| **Pause / Close Menus** | <kbd>Esc</kbd> |

---

## ⚔️ Weapons & Armory

Open the **Armory & Upgrades** screen anytime (<kbd>B</kbd> or on-screen button) to purchase new weapons, upgrade tracks up to Level 5, buy ammo refills, or enhance survivor stats.

| Weapon | Type | Starting Damage | Mag Size | Fire Rate | Description |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **P-11 Pistol** | Semi-Auto | 25 | 10 rounds | ~230 RPM | Reliable sidearm. Cheap to upgrade. |
| **Viper SMG** | Full-Auto | 19 | 32 rounds | 800 RPM | Rapid fire rate; shreds runners and swarms. |
| **Breaker Shotgun** | Pump-Action | 12 × 8 pellets | 6 rounds | ~70 RPM | Devastating point-blank stopping power. |
| **Ranger Rifle** | Full-Auto | 34 | 30 rounds | ~545 RPM | Long range, pinpoint accuracy, heavy stopping power. |
| **Anvil LMG** | Full-Auto | 30 | 100 rounds | ~850 RPM | Massive suppression magazine. High recoil, long reload. |

### Weapon Upgrade Tracks (Up to Level 5)
- **Damage**: Increases projectile damage per hit.
- **Fire Rate**: Decreases delay between shots (increases RPM).
- **Magazine**: Expands clip size and maximum reserve ammo capacity.
- **Reload Speed**: Drastically reduces reload duration.

### Survivor Upgrades
- **Max Health**: Increases maximum survivability (+25 HP per tier).
- **Move Speed**: Increases player movement speed (+6% per tier) to kite hordes.

---

## 🧟 Enemy Types

- **Walker**: Standard infected. Slow-moving in early waves, increases in numbers and aggression.
- **Runner**: Fast, agile rusher designed to flank and overwhelm you.
- **Brute**: High health, heavy mass, and punches through light obstacles.
- **Boss**: Massive milestone monstrosities appearing every 10 waves with colossal health pools.

---

## 🎁 Power-Up Drops

Zombies occasionally drop temporary tactical power-ups:
- **Max Ammo (`A`)**: Instantly refills all weapon magazines and reserves.
- **Double Points (`2×`)**: Doubles all points earned for a limited time.
- **Insta-Kill (`IK`)**: One-shot kills any non-boss zombie for a limited duration.
- **Nuke (`✹`)**: Vaporizes all active zombies currently on the field and awards points.
- **Full Health (`+`)**: Instantly restores the survivor's health to maximum.

---

## 🏆 Global Leaderboard (Supabase Setup)

The game features an online global leaderboard powered by **Supabase**. If Supabase credentials are not configured, it seamlessly falls back to saving scores locally in your browser's `localStorage`.

---

## 🎨 Custom Sprites (Optional)

The game comes with custom procedural canvas drawing for player and zombie models. If you prefer to use PNG sprite sheets (such as Kenney's CC0 *Topdown Shooter* pack), you can link them in the `SPRITES` configuration at the top of the script in `index.html`:

```javascript
const SPRITES = {
  player: "assets/player.png",
  walker: "assets/walker.png",
  runner: "assets/runner.png",
  brute: "assets/brute.png",
  boss: "assets/boss.png"
};
```
*(Images must face right).*

---

## 🛠️ Tech Stack & Implementation Details

- **HTML5 Canvas (2D Context)**: Dynamic camera tracking, particle gore system, obstacle collision detection, radial light vignettes, and custom HUD overlays.
- **Web Audio API**: Real-time sound synthesis with oscillators, white noise buffers, biquad lowpass/bandpass filters, and frequency ramps.
- **Vanilla CSS3**: Cyberpunk-industrial glassmorphism interface, custom CSS variables, and fluid typography.
- **Supabase REST API (PostgREST)**: Lightweight direct HTTP requests for scores without external client libraries.
