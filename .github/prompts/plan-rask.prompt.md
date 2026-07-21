## Implementation Report: Strengthen Risk Build Prompt

Status
- Complete

Objective Achieved
- Replaced the original broad prompt with a structured, implementation-oriented prompt that prioritizes a reliable MVP, explicit rules, and testable acceptance criteria.

Delivered Changes
1. Scope was tightened for MVP reliability:
- Fixed to 2 human players.
- Simplified map requirement (minimum territory and continent structure).
- Deferred AI, sound, and full classic map to post-MVP.

2. Rules were made explicit to reduce ambiguity:
- Reinforcement formula and continent bonus behavior.
- Attack legality, dice caps, tie handling, conquest movement rule.
- Fortification connectivity and troop floor constraints.
- Elimination and immediate victory trigger.

3. Technical constraints were clarified:
- Single HTML file with embedded CSS and JavaScript.
- Vanilla stack only, object-oriented JavaScript, and logic/render separation.
- Full serializable JSON game state and localStorage save/load.

4. UX requirements were converted to testable requirements:
- Required panels and controls defined.
- Invalid action feedback and legal-action clarity required.
- Animation and touch/mouse usability requirements included.

5. Output contract was enforced:
- Phase 1: short implementation plan.
- Phase 2: full single-file code.
- Phase 3: self-check against acceptance checklist.

6. Acceptance checklist was added:
- Browser-run readiness, no build step.
- Full turn-flow correctness.
- Combat and fortify rule correctness.
- Save/load integrity.
- UI state/log/stat consistency.

Files Updated
- c:/temp/rask/rask/startprompt.md

Verification Guidance
1. Run the updated prompt in your coding model.
2. Confirm first response is plan-only, no code.
3. Confirm second response is one complete HTML file.
4. Validate checklist items manually in browser.

Out of Scope (Intentionally Deferred)
1. Full 42-territory map.
2. Third human player mode.
3. AI opponents and extra polish features.

Next Refinement Options
1. Raise visual direction constraints (style tokens, typography direction, animation rhythm) without widening feature scope.
2. Add deterministic map schema examples to further reduce model variation.
3. Create a phase-2 prompt variant dedicated to full-map expansion after MVP passes acceptance.