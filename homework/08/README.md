---
week: 08
neptun: E8671V
---

# Homework 08: Usability test, findings, and mini UI guideline

**Figma prototype (tested version) & Mini UI Guideline:** [HW08 - Posture Assistant tested prototype & UI Guideline](https://www.figma.com/design/3jIp0U0iDkbZ9ZMciE85fr/Design--UX--Ergonomics-Homework?node-id=49-241&t=HmGSkw8XbKOa2vl6-4)

---

## 1. Usability test plan

### Learning goals
1. Evaluate whether university students can complete the core posture-reset flow (starting a focus block, responding to a typing-pause posture cue, and confirming that the reset was logged) without verbal guidance.
2. Identify where passive status indicators, auto-dismiss timing, or secondary states (`90m active`) create hesitation or uncertainty during evening laptop work.

### Participants
- **Participant profile:** 3 students (ages 20–22) who spend 2–4 continuous hours working on laptops in the evening for study, and occasionally experience neck or upper-back stiffness.
- **Prior exposure:** None had seen or tested earlier wireframes of this prototype.

### Scenario and tasks
- **Scenario:** *"It is 10:30 PM and you are finishing a coding or writing assignment on your laptop. You want to avoid neck and back strain over the next couple of hours without having popups interrupt you while you are actively typing."*
- **Task 1 (Session start):** Start a monitored work session, optionally reviewing your desk posture first.
- **Task 2 (Posture cue & confirmation):** When a pause in typing occurs and a posture prompt appears, complete the check and verify that your posture reset was logged.
- **Task 3 (Extended work without pauses):** Check how the assistant behaves if you work for 90 minutes without taking a typing pause, then return to regular monitoring.

### Success criteria and recorded metrics
- **Success criterion:** Participant completes Tasks 1–3 independently without facilitator hints and can confirm whether their posture reset was recorded.
- **Recorded metrics:**
  1. **Completion status** (completed independently / completed with hesitation / incomplete).
  2. **Time on task** (in seconds).
  3. **Misclicks and hesitations** (clicks on non-interactive elements or pauses > 4 seconds).
  4. **Post-task confidence rating** (1–5 scale on how clearly the interface confirmed their action without breaking focus).

---

## 2. Verbal briefing and consent statement

> *"Thank you for helping test this early prototype of a laptop posture assistant. Today I am evaluating the interface—not your skills—so there are no right or wrong actions. The session takes about 5 minutes. I will read you a short scenario and three tasks, and ask you to think aloud as you look at each screen. I will take anonymized written notes on what you click and say without recording your name, face, or personal details. You may pause or stop at any time. Do you agree to take part under these terms?"*

---

## 3. Anonymized observation notes

### Participant P1 (3rd-year student, works on laptop in dormitory evenings)
- **Task 1 — Start session (`01-PreSession-DeskCheck`):**
  - **Observation:** Read all three checklist rows, ticked two boxes (`Laptop near eye level`, `Shoulders relaxed`), and clicked `Start focus block [Enter]` in 7 seconds.
  - **Quote:** `"I like that the desk check is optional—it reminds me to sit up without blocking me from starting."`
  - **Interpretation:** Optional pre-session checkboxes provide useful ergonomic priming without creating onboarding friction.
- **Task 2 — Posture cue & confirmation (`02` → `03` → `04`):**
  - **Observation:** Paused for 6 seconds on `02-ActiveSession-Desktop`, hovered over `Pause` and `End session`, then clicked `[●] Monitoring • 42m`. On `03-CornerCue-Prompt`, clicked `Done [Enter]` within 2 seconds. Squinted when `04-Reset-Confirmation` disappeared after ~1.8 seconds back to `02-ActiveSession-Desktop`.
  - **Quote:** `"Wait, that confirmation disappeared super fast—and the monitoring screen looks the exact same as before, so did it actually save?"`
  - **Interpretation:** Two issues occurred: (1) on `02`, it was unclear how to simulate a typing pause, and (2) `04` vanished too quickly while `02` lacked a persistent `Last reset` indicator.
- **Task 3 — 90-minute no-pause state (`05-State-90Min-NoPause`):**
  - **Observation:** Clicked `Pause` to view `05-State-90Min-NoPause`, read `90m active — stretch when ready`, waited 4 seconds looking for a button, and then clicked the card itself to return.
  - **Quote:** `"It says 'stretch when ready', so I looked around for a button to say I stretched or to close it."`
  - **Interpretation:** A text-only passive card without explicit action buttons leaves users unsure how to acknowledge or dismiss the 90-minute state.

### Participant P2 (2nd-year student, frequently rushes evening assignment deadlines)
- **Task 1 — Start session (`01-PreSession-DeskCheck`):**
  - **Observation:** Ignored the checkboxes and immediately clicked `Skip [Esc]` in 3 seconds.
  - **Quote:** `"If I'm rushing to submit code before midnight, I'm hitting Skip right away."`
  - **Interpretation:** Keeping a clear secondary `Skip` control supports urgent workflows alongside the primary start button.
- **Task 2 — Posture cue & confirmation (`02` → `03` → `04`):**
  - **Observation:** Clicked `End session` first (no response), hesitated 5 seconds, then clicked `[●] Monitoring • 42m`. On `03-CornerCue-Prompt`, clicked `Done [Enter]` immediately, then watched `04-Reset-Confirmation` auto-return to `02`.
  - **Quote:** `"The black Done button is obvious, though at first I wondered why the popup appeared at that exact second."`
  - **Interpretation:** Primary button contrast works well on `03`, but adding a micro-caption (`Triggered during 8s typing pause`) clarifies why the prompt appeared during a break in typing.
- **Task 3 — 90-minute no-pause state (`05-State-90Min-NoPause`):**
  - **Observation:** Opened `05-State-90Min-NoPause`, clicked outside the card once, then clicked inside the card to go back to `02`.
  - **Quote:** `"There's no X or Dismiss button here, so I wasn't sure if it was stuck."`
  - **Interpretation:** Explicit `Take stretch break` and `Dismiss` controls are needed on `05` so users have predictable exit affordances.

### Participant P3 (3rd-year student, alternates between laptop and external display)
- **Task 1 — Start session (`01-PreSession-DeskCheck`):**
  - **Observation:** Checked all three items on `01-PreSession-DeskCheck` and clicked `Start focus block [Enter]` in 8 seconds without hesitation.
  - **Quote:** `"Short and clean—three items is easy to scan."`
  - **Interpretation:** Compact 3-item checklist layout keeps cognitive load low at session start.
- **Task 2 — Posture cue & confirmation (`02` → `03` → `04`):**
  - **Observation:** Scanned `02-ActiveSession-Desktop` for 4 seconds before clicking `[●] Monitoring • 42m`. Clicked `Done [Enter]` in 1.5 seconds on `03-CornerCue-Prompt`. Asked after returning to `02` whether the reset counter had updated.
  - **Quote:** `"Did my posture reset register somewhere, or did nothing change on the monitoring box?"`
  - **Interpretation:** Confirms that returning from `04` to an unchanged `02-ActiveSession-Desktop` leaves users uncertain whether their action had a lasting effect.
- **Task 3 — 90-minute no-pause state (`05-State-90Min-NoPause`):**
  - **Observation:** Reached `05-State-90Min-NoPause`, read the text, paused 3 seconds, and clicked the card to return.
  - **Quote:** `"Having a button to log a stretch break would make this state actually useful."`
  - **Interpretation:** Reinforces adding a primary stretch-confirmation action and secondary dismiss action on `05`.

### Results summary

| Participant | Task | Completion | Time / hesitation | Misclicks | Confidence (1–5) |
| --- | --- | --- | --- | --- | --- |
| P1 | 1 | Completed | 7 s | 0 | not collected |
| P1 | 2 | Completed with hesitation | 6 s pause on `02` | 0 | not collected |
| P1 | 3 | Completed with hesitation | 4 s pause on `05` | 0 | not collected |
| P2 | 1 | Completed | 3 s (used `Skip`) | 0 | not collected |
| P2 | 2 | Completed with hesitation | 5 s pause on `02` | 1 (`End session`) | not collected |
| P2 | 3 | Completed with hesitation | not recorded | 1 (clicked outside card) | not collected |
| P3 | 1 | Completed | 8 s | 0 | not collected |
| P3 | 2 | Completed | 4 s scan on `02` | 0 | not collected |
| P3 | 3 | Completed | 3 s pause on `05` | 0 | not collected |

Confidence ratings were not collected in this round and will be added to the Homework 09 validation check.

---

## 4. Findings ordered by severity

**Severity scale:** 1 = users doubt or cannot confirm the outcome of their action; 2 = users cannot tell how to proceed or exit a state; 3 = users stall or lack context but still complete the task.

**Success criterion verdict:** Not met for confirming the reset. All three participants reached the end of Tasks 1–3, but all three doubted whether the posture reset was saved, and most hesitated or misclicked while finding the cue trigger or leaving state `05`.

**Limitation:** Some hesitation on `02` and `05` comes from prototype shortcuts (the typing pause is simulated by clicking the status line, and `05` is reached via `Pause`), not only from the design itself.

### Severity 1: Overly brief confirmation flash (`04`) and lack of persistent reset status on `02-ActiveSession-Desktop`
- **Evidence:** All 3 participants (P1, P2, P3) questioned whether their posture reset was saved because `04-Reset-Confirmation` disappeared in ~1.8 seconds and returned to an unchanged `02-ActiveSession-Desktop` (`[●] Monitoring • 42m`).
- **Affected task:** Task 2 (Posture cue & confirmation).
- **Consequence:** Users doubt whether their input was recorded, undermining trust and forcing extra visual checks during focused work.

### Severity 2: Missing action and dismissal controls on `05-State-90Min-NoPause`
- **Evidence:** P1, P2, and P3 all hesitated (3–5 seconds) or clicked outside the card on `05-State-90Min-NoPause` because the screen contained only static text (`90m active — stretch when ready`) with no visible buttons.
- **Affected task:** Task 3 (Extended work without pauses).
- **Consequence:** Users cannot tell whether the state requires an action or how to dismiss it cleanly.

### Severity 3: Unclear typing-pause trigger on `02` and missing pause-trigger context on `03-CornerCue-Prompt`
- **Evidence:** P1 (6s), P2 (5s + 1 misclick on `End session`), and P3 (4s) hesitated on `02-ActiveSession-Desktop` figuring out how to trigger the pause state; P2 also noted on `03` that the reason the cue appeared at that moment was not stated.
- **Affected task:** Task 2 (Posture cue & confirmation).
- **Consequence:** Testers stall on `02` during evaluation, and real users may mistake a pause-aware prompt for an arbitrary interruption.

---

## 5. Selected fixes (planned for Homework 09)

1. **Extend the confirmation display to `2800ms` on `04-Reset-Confirmation` and add a persistent `Last posture reset: just now` line on `02-ActiveSession-Desktop`:**
   - **Justification:** Would directly resolve Severity 1 reported across P1–P3.
   - **Comprehensibility & Accessibility note:** A longer display window supports users who read at varied speeds or glance away briefly (aligned with WCAG 2.2.1 Timing Adjustable principles), while `Last posture reset: just now` on `02` keeps system status visible without relying on a fleeting animation.
2. **Add `Take stretch break [Enter]` (primary) and `Dismiss [Esc]` (secondary) buttons to `05-State-90Min-NoPause`:**
   - **Justification:** Would directly resolve Severity 2 reported across P1–P3.
   - **Comprehensibility & Accessibility note:** Replacing an invisible whole-frame click target with explicit, high-contrast buttons (`40px` height) provides clear visual affordance, predictable keyboard navigation (`Enter` / `Esc`), and unambiguous screen-reader roles.
3. **Add a `Triggered during 8s typing pause` micro-caption on `03-CornerCue-Prompt` and a labeled `Simulate 8s typing pause` prototype trigger on `02-ActiveSession-Desktop`:**
   - **Justification:** Would directly resolve Severity 3 (hesitations on `02` and the context question on `03`).
   - **Comprehensibility & Accessibility note:** Stating the trigger condition inside the prompt increases predictability and user trust, while labeling the prototype trigger removes guesswork for testers.

---

## 6. Mini UI guideline (Defined in Figma: `HW08 – Mini UI Guideline`)

All tokens, styles, and component rules are documented visually in the **`HW08 – Mini UI Guideline`** section of the Figma file:

- **Color variables (role-based, WCAG AA compliant, with Dark mode tokens):**
  - `bg/canvas`: `#F4F5F7` (Dark: `#121417`) — Application canvas background.
  - `bg/surface`: `#FFFFFF` (Dark: `#1C1F24`) — Elevated prompt and monitoring card surface.
  - `text/primary`: `#111318` (Dark: `#F3F4F6`) — Primary titles, timers, and labels (**18.7:1** contrast on `bg/surface`, exceeds WCAG AA `4.5:1`).
  - `text/secondary`: `#4B5563` (Dark: `#9CA3AF`) — Helper captions, pause context, and shortcut hints (**7.5:1** contrast on `bg/surface`, exceeds WCAG AA `4.5:1`).
  - `action/primary-bg`: `#111318` + `action/primary-text`: `#FFFFFF` (Dark: `#F3F4F6` / `#111318`) — Single primary CTA fill (**18.7:1** contrast).
  - `border/subtle`: `#D1D5DB` (Dark: `#374151`) — Decorative card outlines and dividers only; never used for control boundaries.
  - `border/control`: `#6B7280` (Dark: `#6B7280`) — Checkbox, outlined-button, and input boundaries (**4.8:1** on light `bg/surface`, **3.4:1** on dark `bg/surface`; meets WCAG 1.4.11 non-text contrast `≥ 3:1`).
- **Text styles:**
  - `Heading / Prompt Title`: 16px SemiBold / 22px line-height (card headers and posture cue titles).
  - `Body / Control Label`: 14px Medium / 20px line-height (checklist labels and button text).
  - `Caption / Meta & Shortcut`: 12px Regular / 16px line-height (pause trigger explanation, `Last posture reset` status, and `[Enter]`/`[Esc]` hints).
- **Spacing scale:**
  - `space-xs = 8px`: Gap between icon and label, or primary label and helper caption.
  - `space-md = 16px`: Internal card padding and gap between stacked action buttons.
  - `space-lg = 24px`: Separation between distinct content blocks (header → body → actions).
- **Button, input, and icon rules:**
  - **Button rule:** Maximum **one** filled `action/primary-bg` button (`40px` height, `8px` radius) per decision screen; all secondary actions (`Skip`, `Snooze 10m`, `Dismiss`) use outlined `border/control` styling so the primary action stands out immediately in peripheral vision.
  - **Input / checkbox rule:** Optional desk-check items use `18×18px` checkboxes (`4px` radius, `border/control`) inside a `≥ 36px` tall clickable row with left-aligned text labels for fast scanning and comfortable click targets.
  - **Icon rule:** Status icons (`16×16px`, `1.5px` stroke, `text/primary`) are **always paired with an explicit text label** (`[●] Monitoring`, `[!] Posture check`, `✓ Posture reset logged`)—never standalone—so state changes do not depend on icon recognition or color alone.
