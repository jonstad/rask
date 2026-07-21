You are generating a complete, playable browser game inspired by Risk.

Objective
- Build a single-file HTML application (embedded CSS + JavaScript) that is fully playable immediately after opening in a browser.
- Prioritize a reliable MVP implementation over feature breadth.

MVP Scope (must ship in first output)
- 2 human players only.
- Simplified map (not full 42-territory classic map) with at least:
  - 12 territories
  - Explicit adjacency graph
  - At least 3 continents/regions with reinforcement bonuses
- Single-page application.
- Responsive layout for desktop and tablet.
- Territory ownership visualization via color coding.
- Troop count visible on each territory.

Non-goals for MVP
- No AI opponents.
- No sound effects.
- No full classic 42-territory map.

Game Rules (explicit behavior)
- Turn phases per player:
  - Reinforcement
  - Attack
  - Fortification
- Reinforcement:
  - Base reinforcement = max(3, floor(ownedTerritories / 3)).
  - Add continent bonuses when a player owns all territories in a continent.
  - Reinforcements can only be placed on owned territories.
- Attack:
  - Attacker can attack only adjacent enemy territories.
  - Attacking territory must keep at least 1 troop behind.
  - Attack dice: attacker rolls 1-3 dice, capped by troops - 1.
  - Defense dice: defender rolls 1-2 dice, capped by defender troops.
  - Compare highest dice pairs in descending order.
  - Defender wins ties.
  - Apply troop losses per pair.
  - If defender reaches 0 troops, attacker conquers territory and must move at least 1 troop in.
- Fortification:
  - Exactly one fortify move allowed per turn.
  - Move troops only between connected owned territories.
  - Must leave at least 1 troop in source territory.
- Elimination and victory:
  - A player is eliminated at 0 territories.
  - Victory triggers immediately when one player controls all territories.

Technical Constraints
- Use only vanilla HTML, CSS, and JavaScript (no external libraries).
- Use object-oriented JavaScript.
- Keep game logic separated from rendering/UI logic.
- Store full game state in a serializable JSON structure.
- Implement save/load using localStorage.
- Include concise comments only where logic is non-obvious.

Required UI Components
- Turn and phase indicator.
- Interactive map with clear selectable/hover/invalid states.
- Dice roll animation for combat resolution.
- Combat log panel with per-battle details.
- Player stats panel (territories, total troops, continent bonuses).
- Territory details panel/popup.
- Reinforcement calculator display for current player.
- Save and load controls.

Interaction and Feedback Requirements
- Show clear visual feedback for legal vs illegal actions.
- Disable or block invalid actions with a short explanation.
- Animate attack resolution and troop movement.
- Ensure all controls are usable with mouse/touch.

Output Contract (follow exactly)
1. First output: a short implementation plan (5-10 bullets), no code.
2. Second output: full single-file HTML code only.
3. Third output: a self-check against the acceptance checklist below.

Acceptance Checklist
- App opens directly in browser with no build step and no console errors.
- Exactly one HTML file includes all CSS and JavaScript.
- 2-player turn cycle works through reinforcement -> attack -> fortification.
- Reinforcement math follows required formula and continent bonus rules.
- Attack legality, dice limits, tie behavior, and conquest logic are correct.
- Fortify connectivity and minimum-troop constraints are enforced.
- Elimination and victory conditions trigger correctly.
- Territory ownership and troop counts update correctly after each action.
- Save/load round-trips full game state correctly.
- Combat log and player stats reflect current state.

Post-MVP Stretch Goals (implement only after MVP is complete and verified)
1. Full 42-territory world map.
2. Optional third human player mode.
3. AI opponents with multiple difficulty levels.
4. Animated map transitions.
5. Sound effects.
6. Undo during reinforcement placement.
7. Expanded statistics dashboard.