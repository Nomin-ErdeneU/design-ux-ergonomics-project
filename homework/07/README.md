---
week: 07
neptun: E8671V
---

# Homework 07: Clickable prototype and first feedback

**Prototype link:** [HW07 - Posture Assistant Prototype](https://www.figma.com/design/3jIp0U0iDkbZ9ZMciE85fr/Design--UX--Ergonomics-Homework?node-id=40-224&t=HmGSkw8XbKOa2vl6-4)

## Scenario and task

- **Scenario:** It is late evening and you have been working on study assignment on your laptop for a while. You want to avoid neck and back strain without breaking your concentration or having popups interrupt you while you are actively typing.
- **Task:** Start your work session, respond when a posture cue appears during a typing pause, and reach the confirmation that your posture reset was logged.

## Main flow, start/success states, and reachable exceptional state

- **Start screen:** `01-PreSession-DeskCheck` (set as the flow starting point with `Start focus block [Enter]` and `Skip [Esc]`).
- **Main flow transitions:** `01-PreSession-DeskCheck` $\rightarrow$ `02-ActiveSession-Desktop` $\rightarrow$ `03-CornerCue-Prompt` (`Done [Enter]`) $\rightarrow$ `04-Reset-Confirmation` (returns automatically after a short delay to `02-ActiveSession-Desktop`).
- **Success state:** `04-Reset-Confirmation` (`Posture reset logged — Returning to monitoring...`).
- **Reachable exceptional state:** `05-State-90Min-NoPause` (reachable from `02-ActiveSession-Desktop` via the `Pause` trigger to inspect the passive `90m active — stretch when ready` state when no typing pause occurs, with a return path back to active monitoring).

## Known limitations of the prototype

- **Simulated typing-pause trigger:** Figma cannot detect real keyboard activity or an 8-second pause in typing, so advancing from `02-ActiveSession-Desktop` to `03-CornerCue-Prompt` requires clicking the `[●] Monitoring • 42m` status area rather than waiting for an actual pause.
- **Keyboard shortcuts are visual labels only:** `[Enter]`, `[Space]`, and `[Esc]` are displayed on buttons to communicate the intended keyboard-first interaction, but all prototype transitions are triggered via mouse or trackpad clicks.
- **Partial interactivity:** Only the primary posture-reset loop and one exceptional state (`05-State-90Min-NoPause`) are wired; secondary controls (`Snooze 10m [Space]`, `Dismiss [Esc]`, `End session`, and the mobile layout variant) are intentionally left non-interactive to keep the trial focused on the main task.
- **Low-fidelity wireframe visuals:** The prototype uses monochrome wireframe frames and static placeholder timer values (`42m`, `90m`) rather than live session timers or real posture tracking.

## Informal trial feedback

### 1. Discovering how to trigger the posture cue on the active monitoring screen
- **Quote:** `"I'm on the monitoring screen now, so do I just wait for the posture reminder or click something?"`
- **Observation:** After clicking `Start focus block [Enter]` on `01-PreSession-DeskCheck`, the participant paused for about five seconds on `02-ActiveSession-Desktop`, hovered between `Pause` and `End session`, and only triggered `03-CornerCue-Prompt` after clicking the `[●] Monitoring • 42m` status line.
- **Interpretation:** Because the prototype cannot simulate real typing inactivity automatically, a static monitoring screen leaves testers unsure how to advance unless a clearly labeled prototype trigger (such as `Simulate 8s typing pause`) is visible during testing.

### 2. Choosing an action on `03-CornerCue-Prompt`
- **Quote:** `"The black button stands out right away, so it's obvious what finishes the check."`
- **Observation:** Once `03-CornerCue-Prompt` appeared, the participant moved the cursor directly to the solid black `Done [Enter]` button and clicked it within two seconds without hesitating over `Snooze 10m [Space]` or `Dismiss [Esc]`.
- **Interpretation:** Using a single high-contrast primary button creates clear visual hierarchy and lets users acknowledge a posture check quickly without breaking their train of thought.

### 3. Reading speed and loop behavior on `04-Reset-Confirmation`
- **Quote:** `"Wait, it disappeared really fast—did it go back to the same session?"`
- **Observation:** After clicking `Done [Enter]`, `04-Reset-Confirmation` flashed briefly and transitioned back to `02-ActiveSession-Desktop` (`[●] Monitoring • 42m`) before the participant finished reading the second line of text.
- **Interpretation:** The confirmation delay is slightly too short for comfortable reading, and because `02-ActiveSession-Desktop` shows the exact same static text before and after the reset, users lack a subtle indicator (like `Last reset: just now`) confirming that the reset was recorded.

## Reflection

- **What was surprising:** Watching the flow without explaining it made it immediately obvious how confusing the transition out of `02-ActiveSession-Desktop` is when real typing-pause detection is missing, as well as how quickly `04-Reset-Confirmation` disappears before a user can read the confirmation message.
- **What was useful:** Testing the clickable loop end-to-end confirmed that the transition from `01-PreSession-DeskCheck` into active monitoring and the single-button hierarchy on `03-CornerCue-Prompt` require zero explanation.
- **What you would change:** I would increase the `After delay` duration on `04-Reset-Confirmation` to around `2.5–3 seconds`, add a small status note on `02-ActiveSession-Desktop` showing the most recent posture reset, and include an explicit `Simulate 8s typing pause` hotspot label during user testing so testers do not have to guess where to click.
