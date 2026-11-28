---
week: 03
neptun: E8671V
---

# Homework 03: Usability and accessibility audit 

**FigJam board:** [Homework 03 - Usability and accessibility audit](https://www.figma.com/board/2NFlEzbSYkC9IR2ieqQkqd/Project---Posture-Ergonomics?node-id=22-1176&t=b79hLHgLbPHyqok8-4)

## Summary

I tested **Morgen Pomodoro Timer** (`morgen.so/pomodoro-timer`) to see how another focus and break timer handles everyday actions compared to my workstation and posture ergonomics assistant. Following the persona from Homework 02 (**Participant A / Student A**), I tried one main flow—opening the timer, checking timer and theme settings, adding a task (`Testing`), switching between `Pomodoro` and `Short break`, and moving around with both the mouse and the keyboard (`Tab`, `Shift+Tab`, `Enter`, `Space`, `Esc`).

## Examined service and task

- **Service:** Morgen Pomodoro Timer (`morgen.so/pomodoro-timer`)
- **Task:** Set up and check timer/theme options, add a task (`Testing`), run/pause/switch between `Pomodoro` and `Short break`, and walk through controls using only the keyboard.
- **For whom and why:** For **Participant A / Student A**—a student who codes and works on coursework for long stretches, often late at night, takes breaks at natural stopping points rather than fixed alarms, and loses around ten minutes of focus when pulled out of deep work. Testing a real timer helps catch design flaws before building our posture and break assistant.

## Main findings (6 findings, including 2 accessibility findings)

1. **Accessibility — Keyboard keys (`WCAG 2.1.1 Keyboard`):** Pressing `Tab` steps forward smoothly and `Shift+Tab` steps backward without getting stuck, but `Space`, `Enter`, and `Esc` did not trigger changes in the actions I tested. When Student A is coding or typing notes and wants to stay on the keyboard, keys not responding forces reaching for the mouse and breaks rhythm. *Fix:* Make `Enter` and `Space` work predictably on controls and let `Esc` close open panels. *(See [screenshot 01: Pomodoro active, 24:37](screenshots/01-pomodoro-active-24-37.png))*
2. **Accessibility — Focus ring vs. active tab (`WCAG 2.4.7 Focus Visible`, `WCAG 1.4.1 Use of Color`):** Tabbing draws a yellow outline around the focused control (like `Short break` at `15:01`), while the active session mode (`Pomodoro` at `24:37`) shows up with lighter/white styling against grey inactive tabs. Late at night with dimmed brightness, Student A has to pause and tell which tab is actually running versus which button just has focus. *Fix:* Keep the yellow focus outline clear and pair the active session with an explicit label or marker so state does not rely mainly on color/fill differences. *(See [screenshot 01: Pomodoro active, 24:37](screenshots/01-pomodoro-active-24-37.png), [screenshot 07: Short break with yellow focus, 15:01](screenshots/07-short-break-yellow-focus-15-01.png))*
3. **Timer length mismatch and hidden settings (*Consistency and Standards* / *Recognition Rather Than Recall*):** Changing durations means opening the right-hand `Settings` drawer, and switching to `Short break` shows `15:01` even though `Short break` is set to `5` min inside `Settings`. For Student A, who already dislikes rigid or surprising timer behavior during work blocks, seeing a different break length or digging into a drawer adds unnecessary friction. *Fix:* Match the shown break duration to the setting and make quick timing adjustments easier to reach. *(See [screenshot 02: Settings, timer and sounds](screenshots/02-settings-timer-and-sounds.png), [screenshot 07: Short break with yellow focus, 15:01](screenshots/07-short-break-yellow-focus-15-01.png))*
4. **Auto-start off by default (*Flexibility and Efficiency of Use*):** Inside `Settings`, `Start the next session automatically` starts turned off, so users have to find and flip it on themselves if they want automatic transitions. Student A could miss a break or be caught off guard depending on how sessions switch. *Fix:* Show auto-advance behavior clearly near the timer so it is obvious how the next block starts. *(See [screenshot 02: Settings, timer and sounds](screenshots/02-settings-timer-and-sounds.png))*
5. **Calendar promo box inside the main screen (*Aesthetic and Minimalist Design*):** The purple `"Put your tasks on your calendar / Plan my day in Morgen"` box sits right under the task card in the lower-right main area during active timer use. During long evening study sessions, an extra promo card adds clutter where Student A wants to focus on one thing. *Fix:* Move calendar promotion to the top bar or footer and keep the active timer and task space clean. *(See [screenshot 01: Pomodoro active, 24:37](screenshots/01-pomodoro-active-24-37.png), [screenshot 05: Pomodoro running, 20:23](screenshots/05-pomodoro-running-20-23.png))*
6. **Long scroll inside `Settings` (*Aesthetic and Minimalist Design*):** The dark look and theme choices (`Default`, `Pixel art`, `Black`, `Navy`, `Forest`) feel easy on the eyes without harsh brightness, but the `Settings` drawer stacks timer inputs, sound sliders (`Rain`, `Fireplace`, `Birds`, `Ocean Waves`), and theme picks into one tall scroll. When Student A is tired late at night and only wants one quick tweak, scrolling through everything slows things down. *Fix:* Split settings into short tabs or groups (`Timer`, `Sounds`, `Theme`). *(See [screenshot 02: Settings, timer and sounds](screenshots/02-settings-timer-and-sounds.png), [screenshot 03: Settings, sounds and theme](screenshots/03-settings-sounds-and-theme.png), [screenshot 04: How Pomodoro works guide](screenshots/04-how-pomodoro-works-guide.png))*

## Deceptive pattern check

- **Observation:** The timer itself does not force an account or hide a paywall (`"Free online study and focus timer. No signup."`), though the `"Plan my day in Morgen"` box sits right in the lower-right workspace as a soft product prompt.
- **Fair alternative:** Keep the timer and task panel focused on the session itself and put Morgen calendar links in the header or footer.

## State list of the examined task

| State | Status | Observation |
| --- | --- | --- |
| **Normal** | Present | Timer countdown (`24:37`, `20:23`, `15:49`, `15:01`), task (`Testing` / `focusing`), and `Pause`, `Reset`, and `Skip ->` buttons are visible. |
| **Loading** | Missing | No loading indicator showed up during task, tab, or settings actions. |
| **Empty** | Weak | The task field has `"What are you working on?"` with no quick hint when starting from scratch. |
| **Error** | Missing | No error or validation message appeared during testing (including when `Space`, `Enter`, and `Esc` did not change state). |
| **Success** | Present | Adding/running a task shows `Testing` with `focusing` in the task list. |
| **Disabled** | Weak | Buttons like `Add`, `Reset`, and `Skip ->` do not show a clear disabled state or key-press feedback. |

## Persona update (from Homework 02)

- **Change:** Added a preference for **low-glare dark themes** and a need for **responsive keyboard keys (`Enter`, `Space`, `Esc`) plus clear active-vs.-focused cues** to **Participant A / Student A**.
- **Why:** Walking through `morgen.so/pomodoro-timer` showed that dark/varied themes help avoid harsh screen glare during focus time, while keyboard behavior and clear state cues affect whether a tired student can control the tool smoothly without losing focus.

## Three risks for our own project

1. **Keyboard actions not responding mid-session:** If Student A tries to snooze or dismiss a posture reminder using `Enter`, `Space`, or `Esc` and nothing happens, they will get annoyed and turn it off. *Prevention:* Support clear keyboard actions and visible focus outlines on controls early on.
2. **Hard-to-read states on a dimmed screen:** Relying mostly on subtle color shifts to show monitoring, break timing, or focus gets tricky at low brightness late at night. *Prevention:* Pair color with clear text or icons and check contrast in dark/low-glare views.
3. **Interruptions or missing states breaking flow:** Extra cards, pushy popups, or missing error/empty states (for instance when posture tracking is off or idle) can break concentration—just like the ~10 minutes of lost focus seen in Homework 02. *Prevention:* Keep the main screen quiet, surface gentle cues around natural task pauses, and include clear empty, error, and disabled states.

## What the board contains

- Examined service and task description
- Six annotated findings with screenshots (including manual keyboard and focus/contrast checks)
- Deceptive pattern check and fair alternative
- State list table (`normal`, `loading`, `empty`, `error`, `success`, `disabled`)
- Updated persona from Homework 02
- Three usability and accessibility risks and preventive ideas for our posture ergonomics project

## Screenshots

- [01-pomodoro-active-24-37.png](screenshots/01-pomodoro-active-24-37.png)
- [02-settings-timer-and-sounds.png](screenshots/02-settings-timer-and-sounds.png)
- [03-settings-sounds-and-theme.png](screenshots/03-settings-sounds-and-theme.png)
- [04-how-pomodoro-works-guide.png](screenshots/04-how-pomodoro-works-guide.png)
- [05-pomodoro-running-20-23.png](screenshots/05-pomodoro-running-20-23.png)
- [06-pomodoro-running-15-49.png](screenshots/06-pomodoro-running-15-49.png)
- [07-short-break-yellow-focus-15-01.png](screenshots/07-short-break-yellow-focus-15-01.png)
