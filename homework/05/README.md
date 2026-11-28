---
week: 05
neptun: E8671V 
---

# Homework 05: Information architecture and user flow

**FigJam board:** [Homework 05 - Information architecture and user flow](https://www.figma.com/board/2NFlEzbSYkC9IR2ieqQkqd/Project---Posture-Ergonomics?node-id=32-2532&t=b79hLHgLbPHyqok8-4)

## Summary

Based on the focus direction chosen in Week 04, I mapped out the minimal structure needed for **Participant A / Student A** to complete a long coding or study session without neck and back strain or broken concentration. I kept the scope strictly to the main task—no calendars, sound mixers, or extra dashboards—checked my UI labels with three people, and mapped the screen hierarchy and user flow including three edge cases.

## Content inventory (ordered by importance)

| Priority | Information / Function | Screen | Why it is needed |
| --- | --- | --- | --- |
| **1** | **Posture / micro-break cue** (text + icon, dark mode) | Corner cue / Menu bar pill | Alerts Student A at natural pauses without breaking deep focus. |
| **2** | **Keyboard controls** (`Done [Enter]`, `Snooze 10m [Space]`, `Dismiss [Esc]`) | Corner cue & Setup card | Lets Student A respond without reaching for the mouse while coding. |
| **3** | **Clear session state** (`Monitoring`, `Snoozed`, `Paused`) | Menu bar pill & Session panel | Shows what the tool is doing at a glance on a dimmed screen. |
| **4** | **Quick 30-second desk check** (laptop height, lower back, screen angle) | Pre-session setup card | Helps fix posture setup before a long session starts. |
| **5** | **Pause / End session controls** | Session panel | Gives full control when switching tasks or finishing work. |
| **6** | **Typing-pause toggle & shortcut hints** | Session panel | Keeps settings minimal while letting Student A control cue behavior. |

## Label check (3 people)

I tested six draft labels with three fellow students by asking what each label meant before showing any screens:

- **`"Natural pause mode"`** was unclear to two people → changed to **`Cue only during typing pauses`**.
- **`"Check shoulders"`** felt too narrow → changed to **`Posture check — sit tall`**.
- Showing the key right inside the button label (**`Done [Enter]`**, **`Snooze 10m [Space]`**, **`Dismiss [Esc]`**) made all three testers immediately see how to use it without a mouse.

## Sitemap

- **Menu Bar / Tray Pill** *(always accessible minimal status)*
  - **Pre-Session 30s Desk Check** *(optional checklist before starting)*
  - **Active Session Panel** *(session status, pause/end, typing-pause toggle)*
  - **Corner Posture Cue Overlay** *(appears only during natural typing pauses)*

## Main screens and supported functions

1. **Menu Bar / Tray Pill:** Displays current status (`Monitoring`, `Snoozed`, `Paused`) using both text and an icon; opens the session panel.
2. **Pre-Session 30s Desk Check:** Optional 3-point posture setup checklist with `Start focus block [Enter]` and `Skip [Esc]`.
3. **Active Session Panel:** Shows active session state, `Pause / Resume`, `End session`, and the `Cue only during typing pauses` toggle.
4. **Corner Posture Cue Overlay:** Quiet dark-mode card in the screen corner triggered only on typing pauses, supporting `Done [Enter]`, `Snooze 10m [Space]`, and `Dismiss [Esc]` with a visible focus ring.

## User flow of the main task

- **Start (User Goal):** Student A wants to finish a 60–90 minute coding/study block without neck or back pain and without losing focus.
- **Main path:** Start focus block → optionally complete or skip (`Esc`) the 30s desk check → work uninterrupted while typing → system detects a natural typing pause → subtle corner cue appears → Student A presses `Enter` (Done), `Space` (Snooze 10m), or `Esc` (Dismiss) → continues working until session end.
- **Decision points:** (1) Complete or skip the 30s desk check at start; (2) Is the user actively typing or in a natural pause; (3) Respond with `Done`, `Snooze`, or `Dismiss`.
- **Three exceptional states (from real risks):**
  1. **Continuous typing for 90+ minutes with no pause:** Instead of interrupting mid-thought with an alarm, the menu bar pill quietly updates its text (`90m active — stretch when ready`).
  2. **Keyboard key missed or low screen brightness:** Every cue button works with both keyboard shortcuts and mouse click, with a clear `:focus-visible` border and text+icon labels.
  3. **Full-screen coding / Do Not Disturb mode:** Cues stay inside the menu bar pill without stealing window focus or covering the editor.

## Wireframes for Homework 06

In Homework 06, I will wireframe the four screens of the main flow: **Pre-Session 30s Desk Check**, **Active Session Panel**, **Menu Bar Status Pill** (normal, snoozed, and 90m warning states), and **Corner Posture Cue Overlay**.
