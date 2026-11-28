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

### Iteration 3: Trigger context on the cue (`Triggered during 8s typing pause`)
- **Evidence (finding):** In Homework 08, P2 asked why the cue appeared at that exact moment on `03-CornerCue-Prompt`, and the cue gave no reason for its timing.
- **Hypothesis:** If `03-CornerCue-Prompt` displays `Triggered during 8s typing pause`, then users will understand why the prompt appears when it does and will not mistake it for an arbitrary interruption.
- **Change:** Added a `Triggered during 8s typing pause` helper line on `03-CornerCue-Prompt`.
- **Rejected alternative:** Leaving the cue with no explanation of its timing—rejected because unexplained prompts make cue timing feel arbitrary.
- **Expected effect:** Clearer mental model of pause-aware prompting and more trust in the cue.
- **Open question:** In the real product, how should brief pauses between sentences be distinguished from a genuine posture-check break?

### Prototype-only change (test aid, not a design iteration)
- Added a labeled `[Simulate 8s typing pause]` trigger on `02-ActiveSession-Desktop` so testers no longer have to guess where to click (Homework 08, Severity 3). The real product would detect typing pauses automatically, so this control is not part of the product design.

---

## 2. Check of modification against success criterion

- **Result: not yet verified.** Only a self-walkthrough has been done so far; the independent-participant check is planned (see section 5).
- **Checked modification:** Iteration 1 & Iteration 2 flow updates (`2800ms` confirmation hold, persistent `Last posture reset: just now` indicator, and explicit `Take stretch break [Enter]` / `Dismiss [Esc]` buttons on `05-State-90Min-NoPause`).
- **Evaluation against success criterion:** Success criterion from HW08 requires completing the core session/cue/reset loop and 90-minute state independently while accurately stating whether the reset was logged. In a structured walkthrough of the updated v2 flow, all steps completed cleanly without guessing how to exit `05-State-90Min-NoPause`, and the `Last posture reset: just now` status remained visible after returning to active monitoring.
- **Limitations:** This verification was performed as a self-walkthrough on the updated Figma prototype rather than a fresh multi-participant lab study, and real hardware telemetry (actual keyboard idle detection and physical posture sensing) remains simulated.

---

## 3. Mini design system (Figma: `HW09 – Mini Design System`)

Organized in a dedicated section/frame in Figma using only components present on the project screens:

- **Buttons (`Button` component set):** Variants for `Primary` and `Secondary` across `Default` and `Focus/Hover` states (`40px` height, `8px` corner radius). Only one primary button is used per decision card.
- **Supporting components:**
  - `Checkbox Row` (`Checked = false` / `Checked = true`, `18×18px` box inside a `≥ 36px` clickable row) for the optional pre-session desk check.
  - `Prompt Card` container (`bg/surface`, `border/subtle`, `8px` radius) for cue and status states.
- **Consistency & reuse:** Tokens (`bg/canvas`, `bg/surface`, `text/primary`, `text/secondary`, `action/primary-bg`, `border/subtle`, `border/control`) and spacing (`8px`, `16px`, `24px`) are shared consistently across components so new screens can be composed without one-off overrides.
- - **Not used in the flow:** The `Input / Field` set and a Disabled button variant exist in the Figma file for future screens, but no current screen uses them.


---

## 4. Handoff screen (`03-CornerCue-Prompt`)

The dedicated handoff frame in Figma presents `03-CornerCue-Prompt` ready for implementation:

- **States shown:** Default prompt state (`[!] Posture check – sit tall`, `Triggered during 8s typing pause`, `Done [Enter]`, `Snooze 10m [Space]`, `Dismiss [Esc]`), focused/active button state, and post-action confirmation (`✓ Posture reset logged` → active monitoring after `2800ms`).
- **Variables & styles referenced:** `bg/surface`, `text/primary`, `text/secondary`, `action/primary-bg`, `border/subtle` (card outline), `border/control` (outlined button borders), typography styles (`16px` SemiBold title, `14px` Medium control label, `12px` Regular caption/shortcut), and spacing (`8px` / `16px` / `24px`).
- **Behavior & accessibility rules:** Triggered only during an 8-second typing pause; single primary CTA (`Done [Enter]`) establishes clear hierarchy; keyboard shortcuts (`Enter`, `Space`, `Esc`) map to primary, snooze, and dismiss actions; icons always pair with text labels and meet WCAG AA contrast (`≥ 4.5:1`). 

---

## 5. Proposed next step

- **Next step:** Run a 3-person validation check specifically focused on the `2800ms` confirmation timing and the new `05-State-90Min-NoPause` buttons (`Take stretch break [Enter]` / `Dismiss [Esc]`) to reduce uncertainty around whether `2800ms` feels slightly sluggish for fast keyboard users during late-evening study blocks. Include the 1–5 confidence rating this time.
