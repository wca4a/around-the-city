# Around the City

A pencil-drawn city exploration game inspired by the original drawing in `assets/original-drawing.png`, with local two-player play, vehicles, shops, and mini-games.

Play online: https://wca4a.github.io/around-the-city/

GitHub Pages serves the game from the repository root. Pushes to the default branch update the live site. The `.nojekyll` file keeps it a plain static website. Saves are stored separately in each browser and origin; localhost progress is not automatically transferred to the hosted version.

Open `index.html` directly in a browser, or run:

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Then visit http://127.0.0.1:8765/.

## Play

- Arrows or WASD: walk or drive. Touch direction buttons also work.
- E: board/leave vehicles, enter/leave buildings, talk to neighbors.
- M: toggle the full city map. Golden markers indicate the current task.
- H: horn, bicycle bell, or say hello.
- Sound button: mute/unmute. Audio begins on your first click or key press.
- Tasks button: show/hide the task card.

Meet Pip in Doodle Park to start six tasks. Progress saves in this browser. Use “Restart the tasks” in the original sketchbook to start over. Boat passengers can disembark at either of the two docks. Drive slowly or stop near the three bus-route stations to register each visit.

The city includes apartments, a hotel, an orchard, a spy lab, shops, subway stations, and many drivable vehicles. Walking limbs, vehicle wheels, boat wakes and train departures animate; optional decorative motion respects the browser's reduced-motion preference. Sounds use local Web Audio synthesis without external assets.

## Verify

```sh
node --check game.js
node tests/game.test.cjs
```

The simulation test covers all interiors, the complete quest sequence, vehicle movement, dock interactions, subway travel, NPC movement, map rendering and reduced-motion rendering. Browser checks cover startup, boarding, audio initialization and the UI.
