---
week: 04
neptun: E8671V
---

# Homework 04: Problem definition and opportunity search

**FigJam board:** [Homework 04 - Problem definition and opportunity search](https://www.figma.com/board/2NFlEzbSYkC9IR2ieqQkqd/Project---Posture-Ergonomics?node-id=30-2217&t=b79hLHgLbPHyqok8-4)

## Summary

Based on my problem map (Week 01), student interview and persona (Week 02), and timer audit (Week 03), I narrowed the project down to one testable focus: helping students prevent neck and back strain during long evening laptop sessions without breaking concentration. I wrote four "How Might We...?" questions, came up with eight solution ideas, and ranked them on an Impact vs. Feasibility matrix while separating research evidence (`[Evidence]`) from unverified assumptions (`[Assumption]`).

## One-page project brief

- **Problem (`[Evidence]`):** During 2+ hour evening laptop sessions, students' posture slowly slumps without them noticing, while fixed timers and popups break deep focus (costing ~10 minutes) and get dismissed or deleted.
- **Target user (`[Evidence]`):** University students (**Participant A / Student A**) coding or studying on a laptop late at night at a small or low desk.
- **Primary task (`[Evidence]`):** Finish a focused 60–90 minute study/coding block while noticing and responding to gentle, keyboard-accessible posture and micro-break cues at natural pauses without losing focus.
- **Organizational goal (`[Assumption]`):** Build a lightweight posture assistant that students keep enabled over weeks because it reduces strain without feeling like an annoying timer.
- **Constraints:** Cues cannot break concentration (`[Evidence]`); controls must work from the keyboard (`Enter`, `Space`, `Esc`) in dark mode with text+icon states (`[Evidence]`); all processing stays local (`[Assumption]`).
- **Success criterion (`[Evidence]`):** In a 60+ minute test session, participants hold neutral posture longer than without the tool and rate disruption **2 or less on a 5-point scale**.
- **Exclusions:** Calendar planners and sound mixers (`[Evidence]`), medical advice or chair hardware (`[Assumption]`), and forced screen lockouts or loud alarms (`[Evidence]`).

## Stakeholder table

| Stakeholder | Role / Interest | What they need | Basis |
| --- | --- | --- | --- |
| **Student (Student A)** | Primary user working long laptop sessions | Less neck/back stiffness without breaking focus or screen glare | `[Evidence]` |
| **Project Team (Me)** | Designs and tests the semester prototype | A narrow, testable single-task scope that works well on keyboard | `[Evidence]` |
| **Course Instructor** | Evaluates research rigor and scope | Clear link from evidence to HMWs, matrix choices, and test criteria | `[Evidence]` |
| **Roommates / Study Peers** | Share dorm or study spaces at night | Silent, non-disruptive cues instead of loud alarms | `[Assumption]` |

## User story and problem statement

- **User story (`[Evidence]`):** As a student coding on my laptop late at night, I want gentle, dark-mode posture and micro-break cues at natural stopping points that I can control from my keyboard, so I avoid neck and back stiffness without losing my train of thought.
- **Problem statement (`[Evidence]`):** The problem of **university students working in long laptop sessions** is that **their posture gradually gets worse without them noticing while fixed timers and popups interrupt their focus and get dismissed**, because of which **neck and back pain builds up until the session ends**.

## How Might We...? questions

1. **HMW 1:** How might we show posture or break cues around natural task pauses so Student A doesn't lose ~10 minutes of focus? (`[Evidence]`)
2. **HMW 2:** How might we help students notice neck and shoulder slump early before pain starts? (`[Evidence]`)
3. **HMW 3:** How might we let keyboard-first students check, snooze, or dismiss a cue on a dimmed screen without reaching for the mouse? (`[Evidence]`)
4. **HMW 4:** How might we make posture feedback feel supportive and optional so it doesn't get deleted after one interruption? (`[Evidence]`)

## Solution ideas (8 directions)

1. **Pause-based corner cue (`[Evidence]` + `[Assumption]`):** Watches for natural typing/mouse pauses (code compiling, tests running) and shows a quiet corner cue instead of interrupting active typing.
2. **Soft screen-edge tint (`[Evidence]` + `[Assumption]`):** Slowly warms the screen edge when slump lasts too long—no popup box or sound.
3. **One-key dismiss/snooze (`[Evidence]`):** Lets Student A press `Esc` or `Space` to snooze or acknowledge a cue with a clear focus ring.
4. **Quick 30-second desk check at start (`[Evidence]`):** Optional checklist before starting (raise laptop, pillow behind lower back, screen angle).
5. **Local webcam angle check (`[Evidence]` + `[Assumption]`):** Uses the laptop camera locally (never uploaded) to flag forward head tilt after 15+ minutes.
6. **End-of-task stretch prompt (`[Evidence]`):** Waits until a task finishes or typing stops for 60 seconds before suggesting one 30-second stretch.
7. **Tiny dark-mode menu bar pill (`[Evidence]`):** Shows posture status (`OK` / `Check shoulders`) with both an icon and text—not color alone.
8. **1-click end-of-session check-in (`[Assumption]`):** Asks "How do your neck and back feel?" when closing the session to track comfort over time.

## 2×2 prioritization matrix (Impact vs. Feasibility)

| Quadrant | Ideas | Why |
| --- | --- | --- |
| **High Impact / High Feasibility (Do First)** | **#1 Pause-based corner cue**, **#3 One-key dismiss/snooze**, **#4 Quick 30s desk check**, **#7 Tiny dark-mode status pill** | Directly solves focus protection, keyboard control, and low-glare clarity (`[Evidence]`). |
| **High Impact / Lower Feasibility (Test Later)** | **#5 Local webcam angle check**, **#2 Soft screen-edge tint** | Useful, but low-light camera accuracy, privacy, and OS overlays add risk (`[Assumption]`). |
| **Lower Impact / High Feasibility (Nice to Have)** | **#6 End-of-task stretch prompt**, **#8 1-click session check-in** | Good extras once core pause-aware cues work (`[Evidence + Assumption]`). |
| **Lower Impact / Lower Feasibility (Skip)** | Calendar planners, sound mixers, forced lockouts | Caused clutter or deletion in Weeks 2–3 (`[Evidence]`). |

## Chosen direction and justification

I am taking forward a **keyboard-friendly, dark-mode posture and micro-break helper triggered at natural pauses** (combining **#1, #3, #4, and #7**). Week 2 showed that fixed alarms get deleted and popups cost ~10 minutes of focus, while real breaks happen at natural task boundaries. Week 3 showed that dark mode, clear text+icon states, and working keyboard keys (`Enter`, `Space`, `Esc`) matter most during coding. Skipping the webcam at first keeps the prototype private, simple, and ready to test in a 60-minute session (`[Evidence]` + `[Assumption: pause cues alone improve posture]`).
