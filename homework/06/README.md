---
week: 06
neptun: E8671V
---

# Homework 06: Low-fidelity wireframe

**Figma file:** [HW06 - Posture Assistant Wireframes](https://www.figma.com/design/3jIp0U0iDkbZ9ZMciE85fr/Design--UX--Ergonomics-Homework?node-id=40-232&t=HmGSkw8XbKOa2vl6-4)

## Overview

Based on the sitemap and user flow from Homework 05, I built black-and-white low-fidelity wireframes in Figma using basic shapes, text placeholders, and Auto Layout. The file covers the main task flow from the pre-session desk check to confirmation, desktop and mobile views of the active session screen, two exceptional states, flow arrows, and notes on screen behavior.

## Screens and states

- **`01-PreSession-DeskCheck` (Start decision):** Optional 3-item posture check (`Laptop near eye level`, `Lower back supported`, `Shoulders relaxed`) with `Start focus block [Enter]` as the main action and `Skip [Esc]` to bypass it.
- **`02-ActiveSession-Desktop` & `02-ActiveSession-Mobile` (Main screen — desktop & mobile):** Shows the active session timer (`Monitoring • 42m`), the `Cue only during typing pauses` toggle, and `Pause` / `End session` controls on both desktop and mobile layouts.
- **`03-CornerCue-Prompt` (Main decision screen):** Non-blocking posture prompt (`Posture check – sit tall`) shown during a typing pause, with `Done [Enter]` as the primary action and `Snooze 10m [Space]` / `Dismiss [Esc]` as secondary actions.
- **`04-Reset-Confirmation` (Confirmation):** Short confirmation (`Posture reset logged — Returning to monitoring...`) before returning to active monitoring.
- **`05-State-90Min-NoPause` (Exceptional state — no pause):** If the user types for 90+ minutes without pausing, the status updates to `90m active – stretch when ready` instead of interrupting active typing.
- **`06-State-Empty-NoSession` (Exceptional state — empty state):** Idle screen before a session starts (`No active session`) with a single `Start focus block [Enter]` button.

## Notes on layout logic, main action, and hierarchy

- **Content hierarchy:** Each screen highlights the current status and one primary keyboard action (`Start focus block [Enter]` or `Done [Enter]`) using a solid black fill, while secondary options (`Skip [Esc]`, `Pause`, `End session`, `Snooze 10m [Space]`, `Dismiss [Esc]`) use light outlines so everything does not compete equally.
- **Main action & flow:** Posture prompts appear only during typing pauses (8+ seconds) so they do not steal focus while coding or writing. Arrows and note boxes show how each button moves to the next screen or returns to monitoring.
- **Auto Layout & naming:** Frames and layers are named `01`–`06` to match the flow, and Auto Layout stacks keep button padding and alignment consistent when resizing between desktop and mobile screens.
