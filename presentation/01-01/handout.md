# CornerCue: a posture reminder that does not interrupt your focus

**Presenter:** Nomin-Erdene Ugiidalai
**Week and topic:** Project presentation, UX/UI Design (Homework 10)
**Presentation:** [PWMD source]()

## Short Summary

CornerCue is a design project for students who work for hours on a laptop. It aims to reduce neck and back strain without breaking concentration, because fixed break timers interrupt deep work and are usually dismissed. The result so far is a clickable Figma prototype, tested with three students and improved once.

## Explanation of the Core

Students working late often slouch without noticing, but a timer that rings in the middle of a hard problem costs about ten minutes of focus, according to my interview. CornerCue therefore waits for a natural pause in typing (about 8 seconds in the prototype) and then shows a small card in the screen corner. The student answers with one key: `Enter` for Done, `Space` to snooze for 10 minutes, or `Esc` to dismiss.

For example, a student is coding at night, the tests start running and typing stops, the card appears, and the student presses `Enter` and sees "Posture reset logged". In the usability test, all three participants found the Done button within about two seconds. However, the confirmation vanished after roughly 1.8 seconds and the next screen looked unchanged, so all three doubted that the reset was saved. I extended the confirmation to 2800 ms and added a permanent "Last posture reset" line. This was checked only by walking through the prototype myself, not yet with new participants.

## Main Takeaways

- Show a posture cue only at a natural pause, never in the middle of typing.
- Always confirm an action in a way the user has time to read and that stays visible afterwards.
- Every state needs a visible way out, such as a button to dismiss it.
- Three participants and a simulated typing pause are limits; the findings are early evidence, not proof.

## Concepts Learned

- **Persona:** A fictional but research-based profile of a typical user that guides design decisions.
- **How Might We question:** An open question that turns a problem into a design opportunity.
- **Impact/feasibility matrix:** A 2×2 chart that ranks ideas by expected benefit and by how easy they are to build.
- **Usability test:** Observing real users as they try tasks on a prototype, to see where they hesitate, err, or fail.
- **Severity rating:** A scale that ranks findings by how much they harm the user's task.
- **Non-text contrast (WCAG 1.4.11):** Interface parts such as control borders and icons need at least 3:1 contrast against their surroundings.
- **Design token:** A named value, such as a color or spacing size, that is reused across components for consistency.
