# ⛵ Code Odyssey

**Your journey from first step to algorithm.**

Code Odyssey is a browser game that teaches **Computational Thinking**. Learners sail across an archipelago of **12 islands**, each built around one Computational Thinking idea. Every island has **3 sub-stages**, 36 in total. In each one, learners guide an agent through a puzzle by dragging and dropping blocks. There is no typing and there are no syntax errors.

The whole app is a single `index.html` file. It needs no installation, internet connection, accounts or external libraries. It runs on desktop browsers and on iPad (Safari and Chrome).

Created by **Khiew Tzong Yong**, School of EIT, ITE College West.

---

## Quick start

| Goal | What to do |
| --- | --- |
| Play locally | Double-click `index.html` to open it in Chrome, Edge, Safari or Firefox. It works offline from `file://`. |
| Host on GitHub Pages | Commit `index.html` to the repository root, then go to **Settings → Pages → Source: main branch / (root)**. The game is then at `https://<username>.github.io/<repository-name>/`. |
| Install on an iPad Home Screen | Open the hosted page in Safari, tap **Share → Add to Home Screen**. It appears as "Code Odyssey". |

---

## How to play

1. **Captain's Briefing.** The first time the app is opened on a device, Captain Algo explains Computational Thinking in 8 short pages. You can replay the briefing at any time from **ℹ️ About**.
2. **World Map.** Click an unlocked island. Locked islands show 🔒. Hover over any island (or long-press it on a touch screen) to see Captain Algo explain that island's objective and learning outcome.
3. **Island View.** Choose a sub-stage: **.1 Intro**, **.2 Pattern** or **.3 Mastery**.
4. **Workbench.** Drag blocks from the palette into the program area, or tap a palette block to add it. Then press **▶ Run Code** and watch the agent follow your instructions.
5. **Fix and retry.** If something goes wrong, read the console at the bottom right, change your blocks and run again.

### Stars

| Stars | How to earn them |
| --- | --- |
| ⭐ | Clear all of the puzzle's objectives |
| ⭐⭐ | Also stay within the target number of steps |
| ⭐⭐⭐ | Also use no more than the optimal number of blocks |

Clearing all 3 sub-stages on an island unlocks the next island. There are **108 stars** to collect in total.

### Workbench tips

- **Block categories:** ⚡ Action, 🔁 Control, 📝 Variable, 📡 Sensor, 🏗 World. Each tab only shows the blocks that the current sub-stage needs.
- **Conditions:** drag a Sensor chip (for example `isPathClear`, or `NOT` / `AND` / `OR`) into the condition socket of an **If** or **While** block.
- **Nesting:** Repeat, While, If, If-Else, Define and For Each blocks have slots that can hold other blocks.
- **Deleting a block:** drag it back onto the palette.
- **Speed slider:** 🐢 to 🐇 sets how fast the agent moves.
- **💡 Hint:** the first tap shows a hint in the console. The second tap offers to load the reference 3-star solution. Teachers may find this useful; students can use it too.
- **Coordinates:** tile numbers run along the top and left edges of the map. You need them on the World Build and Arrays islands.

### Keyboard shortcuts

| Key | Action |
| --- | --- |
| `Ctrl` / `Cmd` + `Enter` | Run the program (Workbench) |
| `→` or `Enter` | Next page (briefing) |
| `←` | Previous page (briefing) |
| `Esc` | Skip the briefing, or close About or the victory window |

---

## Curriculum

| Island | Concept | Sub-stages (.1 Intro · .2 Pattern · .3 Mastery) |
| --- | --- | --- |
| ⚔️ 1. Commands | Sequential Decomposition | First Step · Right Turn · Castle Maze |
| 📦 2. Functions | Abstraction & Code Reuse | Double Step · Corner Cleaner · Twin Towers |
| 🔁 3. For Loops | Fixed Iteration & Patterns | Four Steps · Square Garden · Staircase Climb |
| 🔀 4. Conditionals | Decision Making with If / Else | Open Door · Gem vs Switch · Random Corridor |
| ⚡ 5. Logicals | Compound Conditions: AND, OR, NOT | Safe Path · Double Sensor · Trap Avoidance |
| ♾️ 6. While Loops | Conditional Iteration | Walk to Wall · Gem Search · Maze Runner |
| 🧩 7. Algorithms | Universal Problem-Solving | Wall Follower · Spiral Collector · The Grand Escape |
| 💎 8. Variables | State Tracking & Data Storage | Gem Counter · Step Tracker · Vault Code |
| 🎨 9. Types | Types & Object Properties | Speed Boost · Color Shield · Multi-Agent Control |
| 🎛️ 10. Parameters | Function Customization | Parameterized Move · Shape Drawer · Attack & Move |
| 🏗️ 11. World Build | Dynamic Map Editing | Bridge Builder · Portal Placer · Custom Maze Creator |
| 📊 12. Arrays | Indexed Data & Collections | Coordinate List · Inventory Filter · Waypoint Master |

Some sub-stages are built to reward general solutions rather than memorised ones:
- **Random layouts:** 4.2, 4.3, 5.2 and 6.2 change their layout every time you press Run, so the program has to use sensors.
- **Multiple mazes:** 7.3 runs the same program on 3 different mazes.

The four pillars of Computational Thinking (Decomposition, Pattern Recognition, Abstraction and Algorithms) are introduced in the Captain's Briefing and summarised in the About window.

---

## Saved progress

Progress is saved automatically in the browser's `localStorage`, separately on each device and in each browser.

| Key | Contents |
| --- | --- |
| `ctquest_v3_progress` | Unlocked islands, best star rating for each sub-stage, saved programs and the speed setting |
| `codeodyssey_intro_seen` | `"1"` once the Captain's Briefing has been completed or skipped |

- If `localStorage` is unavailable (for example in some private browsing modes), the app keeps progress in memory for the current session.
- **↺ Reset Progress** on the World Map erases both keys, so the briefing appears again on the next load.

> The progress key still carries the app's original working name. **Do not rename it**, or students will lose their saved progress.

---

## Customising

All settings are inside `index.html` and can be edited with any text editor.

| What | Where to find it |
| --- | --- |
| Creator name and school (About footer) | `APP_AUTHOR`, `APP_CREDIT` |
| Version shown in About | `APP_VERSION` |
| Captain's Briefing text | `BRIEFING_PAGES` (8 pages: title, text and an optional "key idea" chip) |
| Island names, icons and map positions | `WORLD_ISLANDS` |
| Levels: maps, available blocks, objectives, hints, reference solutions | `SUBSTAGE_DATA` |

In `SUBSTAGE_DATA`, each level's map is 12 rows of 16 characters. The legend is in the comment above it. Each level's reference solution:
- is written in a short text format, for example `repeat(4) { move(3) right }`
- sets that level's ⭐⭐ and ⭐⭐⭐ targets.

If you change a map, check that its reference solution still clears it.

---

## Project structure

```
index.html          The complete app: inline CSS, HTML and JavaScript
README.md           This file
spec/               Original design specification (PRD, UI, content, engine, acceptance tests, prompts)
```

`index.html` is organised into labelled sections:

1. Constants & game state, including the curriculum data
2. Storage & map navigation
3. Canvas renderers: World Map, Island View, Puzzle Grid
4. Drag & drop block engine
5. Puzzle interpreter: runs programs, checks objectives, awards stars
6. UI modals & overlays: victory, Captain's Briefing, About
7. Initialisation & boot

The game logic in sections 1 and 5 does not touch the page, so it can be tested on its own in Node.js.

---

## Browser support

| Device | Layout |
| --- | --- |
| **Desktop** (Chrome, Edge, Firefox, Safari) | Map and blocks side by side (62% / 38%) |
| **iPad** (Safari / Chrome, iPadOS 13+) | Side by side in landscape; stacked in portrait. Touch drag-and-drop. |
| **Phones in portrait** (iPhone, Android) | The World Map and Island View switch to tall layouts with larger tap targets. The Workbench stacks the map above the blocks, uses short button labels, and starts with the objectives collapsed (tap **▸ show**). |
| **Phones in landscape** | Compact side-by-side Workbench with slimmer bars and console |
| **Folding phones** (Galaxy Z Fold / Z Flip) | The cover screen uses the phone layout. Unfolded, the app uses the full inner screen in either orientation. |
| **Dual-screen and spanned foldables** | On browsers that support the Viewport Segments API, the puzzle and the blocks each stay on their own screen, and dialogs never sit across the hinge. Side-by-side screens put the puzzle on the left and the blocks on the right. A half-folded "tabletop" device puts the puzzle on top and the blocks below. |

On phones and foldables:
- Tapping a palette block adds it straight to your program, which is quicker than dragging on a small screen.
- Long-pressing a block does not open the phone's context menu.

**Tested sizes** (Chrome mobile emulation with real touch input):
- Phones: 344×882 (Fold cover), 360×740, 390×844, 412×915 (Z Flip)
- Fold unfolded: 673×841 and 841×673
- Landscape phones: 667×375 and 844×390
- Emulated hinges: dual-screen 1114×705 and tabletop 720×1114

Testing used emulation only. Before relying on a specific model in class, check it on the real device.

---

## Credits

Designed and created by **Khiew Tzong Yong**, School of EIT, ITE College West.

All graphics, including Captain Algo, are drawn in code with HTML5 Canvas, inline SVG and CSS. The app uses no external images, fonts, audio or libraries.
