---
week: 09
neptun: E8671V
---

# Homework 09: Iteration, components, and a mini design system

**Figma link (Iterated prototype, Mini Design System & Handoff):** [HW09 - Posture Assistant Design System & Handoff](https://www.figma.com/design/3jIp0U0iDkbZ9ZMciE85fr/Design--UX--Ergonomics-Homework?node-id=62-143&t=HmGSkw8XbKOa2vl6-4)

---

## 1. Iteration decision log

### Iteration 1: Persistent post-reset status (`Last posture reset: just now`) and extended confirmation hold (`2800ms`)
- **Evidence (finding):** In Homework 08 usability testing (P1–P3), `04-Reset-Confirmation` auto-dismissed in ~1.8s and returned to an unchanged `02-ActiveSession-Desktop`, leading participants to doubt whether their posture reset had been recorded.
- **Hypothesis:** If `04-Reset-Confirmation` stays visible for `2800ms` and `02-ActiveSession-Desktop` displays a persistent `Last posture reset: just now` status line after a reset, then participants will confirm their reset was saved without hesitation or repeat checks.
- **Change:** Increased the `After delay` transition on `04-Reset-Confirmation` to `2800ms` and added a persistent `Last posture reset: just now` status line on the post-reset `02-ActiveSession-Desktop` state.
- **Rejected alternative:** Leaving the `1800ms` auto-dismiss timer unchanged and relying solely on a toast popup—rejected because fast dismissal plus an identical return screen failed to reassure users during evening focus.
- **Expected effect:** Higher confidence that posture resets are registered and fewer post-confirmation hesitations.
- **Open question:** Does `2800ms` feel slightly too slow for fast keyboard-only users who press `Enter` and immediately resume typing?

### Iteration 2: Explicit action buttons (`Take stretch break [Enter]` and `Dismiss [Esc]`) on `05-State-90Min-NoPause`
- **Evidence (finding):** In Homework 08 (P1–P3), `05-State-90Min-NoPause` showed only static text (`90m active — stretch when ready`), causing 3–5s hesitations and off-card clicks as participants looked for how to log a stretch or close the notice.
- **Hypothesis:** If `05-State-90Min-NoPause` provides a primary `Take stretch break [Enter]` button and a secondary `Dismiss [Esc]` button, then users will complete or dismiss the 90-minute check cleanly without guessing how to exit.
- **Change:** Added a primary `Take stretch break [Enter]` button (routed to `04-Reset-Confirmation`) and a secondary `Dismiss [Esc]` button (routed back to `02-ActiveSession-Desktop`) on `05-State-90Min-NoPause`.
- **Rejected alternative:** Making the entire card clickable with no visible buttons—rejected because an invisible target lacks clear affordance, keyboard clarity, and distinct stretch vs. dismiss outcomes.
- **Expected effect:** Zero ambiguity on how to acknowledge a stretch break or dismiss the 90-minute reminder.
- **Open question:** Should `Take stretch break [Enter]` start a short guided timer or go straight to reset confirmation?

### Iteration 3: Explicit typing-pause trigger & trigger context (`Triggered during 8s typing pause`)
- **Evidence (finding):** In Homework 08, participants hesitated on `02-ActiveSession-Desktop` (with one misclick on `End session`) when trying to trigger a typing pause in the prototype, and P2 asked why the cue appeared at that exact moment on `03-CornerCue-Prompt`.
- **Hypothesis:** If `02-ActiveSession-Desktop` includes a clear `[Simulate 8s typing pause]` prototype trigger and `03-CornerCue-Prompt` displays `Triggered during 8s typing pause`, then testers and users will understand both how the prototype simulates a pause and why the prompt appears then.
- **Change:** Added a `[Simulate 8s typing pause]` trigger on `02-ActiveSession-Desktop` and a `Triggered during 8s typing pause` helper line on `03-CornerCue-Prompt`.
- **Rejected alternative:** Keeping the typing-pause trigger hidden inside the monitoring badge with no explanation text on `03`—rejected because hidden triggers stall evaluation and make cue timing feel arbitrary.
- **Expected effect:** Faster, lower-error flow progression and clearer mental model of pause-aware prompting.
- **Open question:** In the real product, how should brief pauses between sentences be distinguished from a genuine posture-check break?

---

## 2. Check of modification against success criterion

- **Checked modification:** Iteration 1 & Iteration 2 flow updates (`2800ms` confirmation hold, persistent `Last posture reset: just now` indicator, and explicit `Take stretch break [Enter]` / `Dismiss [Esc]` buttons on `05-State-90Min-NoPause`).
- **Evaluation against success criterion:** Success criterion from HW08 requires completing the core session/cue/reset loop and 90-minute state independently while accurately stating whether the reset was logged. In a structured walkthrough check of the updated v2 flow, all steps completed cleanly without guessing how to exit `05-State-90Min-NoPause`, and the `Last posture reset: just now` status remained visible after returning to active monitoring.
- **Limitations:** This verification was performed as a self-walkthrough on the updated Figma prototype rather than a fresh multi-participant lab study, and real hardware telemetry (actual keyboard idle detection and physical posture sensing) remains simulated.

---

## 3. Mini design system (Figma: `HW09 – Mini Design System`)

Organized in a dedicated section/frame in Figma using only components present on the project screens:

- **Buttons (`Button` component set):** Variants for `Primary`, `Secondary`, and `Disabled` across `Default` and `Focus/Hover` states (`40px` height, `8px` corner radius). Only one primary button is used per decision card.
- **Input fields (`Input / Field` component set):** Variants for `Default`, `Focus`, and `Error` states (with visible focus outline and clear validation/error message slot) for numeric session/interval inputs.
- **Supporting components:**
  - `Checkbox Row` (`Checked = false` / `Checked = true`, `18×18px` box inside a `≥ 36px` clickable row) for the optional pre-session desk check.
  - `Prompt Card` container (`bg/surface`, `border/subtle`, `8px` radius) for cue and status states.
- **Consistency & reuse:** Tokens (`bg/canvas`, `bg/surface`, `text/primary`, `text/secondary`, `action/primary-bg`, `border/subtle`) and spacing (`8px`, `16px`, `24px`) are shared consistently across components so new screens can be composed without one-off overrides.

---

## 4. Handoff screen (`03-CornerCue-Prompt`)

The dedicated handoff frame in Figma presents `03-CornerCue-Prompt` ready for implementation:

- **States shown:** Default prompt state (`[!] Posture check – sit tall`, `Triggered during 8s typing pause`, `Done [Enter]`, `Snooze 10m [Space]`, `Dismiss [Esc]`), focused/active button state, and post-action confirmation (`✓ Posture reset logged` $\rightarrow$ active monitoring after `2800ms`).
- **Variables & styles referenced:** `bg/surface`, `text/primary`, `text/secondary`, `action/primary-bg`, `border/subtle`, typography styles (`16px` SemiBold title, `14px` Medium control label, `12px` Regular caption/shortcut), and spacing (`8px` / `16px` / `24px`).
- **Behavior & accessibility rules:** Triggered only during an 8-second typing pause; single primary CTA (`Done [Enter]`) establishes clear hierarchy; keyboard shortcuts (`Enter`, `Space`, `Esc`) map to primary, snooze, and dismiss actions; icons always pair with text labels and meet WCAG AA contrast (`≥ 4.5:1`). *(Marked as handoff-ready in the frame label; Figma Free plan does not enable native Dev Mode status toggles.)*

---

## 5. Proposed next step

- **Next step:** Run a 3-person validation check specifically focused on the `2800ms` confirmation timing and the new `05-State-90Min-NoPause` buttons (`Take stretch break [Enter]` / `Dismiss [Esc]`) to reduce uncertainty around whether `2800ms` feels slightly sluggish for fast keyboard users during late-evening study blocks.
