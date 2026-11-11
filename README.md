# BLACKOUT

A terminal infiltration game made for **GMTK Game Jam 2026** (theme: *Countdown*).

You're a hacker breaching five hardened systems. Use real Unix-style commands to steal the data and erase your traces before the detection timer runs out. On the final system, the tables turn.

🎮 **Play it on itch.io:** [kinacahmet.itch.io/blackout](https://kinacahmet.itch.io/blackout)

## Features

- **Unix-style commands:** `ls`, `cd`, `cat`, `grep`, `rm`, `sort`, `uniq`, `lock`, `help`
- **Five levels**, each introducing a new mechanic: searching with `grep`, wiping logs with `rm`, filtering noise with `sort` and `uniq`
- **Two-phase finale:** Cracking the master password triggers a counter-attack, and you must defend critical files before time runs out
- **Zero assets:** Single HTML file; all sound effects are generated in code

## Technical Overview

- **Data-driven level design:** Each level is a single config object (virtual file system, timer, objectives, traps). Adding a level means adding an object to the `LEVELLER` array; no game logic changes.
- **Virtual file system:** Folders and files are nested JavaScript objects. Each level loads a fresh deep copy, so retries restore deleted files.
- **Procedural audio:** Keyboard clicks, alarms and win/lose jingles are synthesized at runtime with the Web Audio API (oscillators and filtered noise).
- **No dependencies:** Plain HTML, CSS and JavaScript.

## Run Locally

Open `index.html` in any modern browser. Best played on desktop with a keyboard.

## Credits

Designed and developed by Ahmet Kinac.