<!--@slide Opening-->
# CornerCue: Evidence-Based Posture Prompt Design

Why do university students ignore posture apps during multi-hour evening laptop sessions—and how can a pause-aware corner cue fix it?

---

<!--@slide Problem and Target User-->
# Fixed-Timer Alerts Break Deep Study Flow

- **Target user:** University students working 3–5+ hours in the evening on laptops
- **Core pain points:** Forward neck slump, shoulder fatigue, and intrusive modal popups
- **Why chosen:** Existing posture tools interrupt mid-sentence, causing instant dismissal

---

<!--@slide Research Lessons-->
# Users Dismiss Alerts That Interrupt Active Typing

- **Observation ($n = 5$ student sessions):** 4 of 5 participants closed timer popups immediately when typing code or essays
- **Key insight:** Willingness to adjust posture spikes during natural 6–10 second micro-pauses
- **Sample limitation:** Small sample ($n = 5$) from one university cohort limits broad generalization

---

<!--@slide Persona and Journey-->
# Evening Student Persona & High-Friction Moment

```mermaid
flowchart LR
    A[Start Evening Session] --> B[90m Deep Typing]
    B --> C[Neck & Shoulder Slump]
    C --> D{Fixed Timer Popup?}
    D -- Interrupts typing --> E[Dismissed & Ignored]
    D -- 8s Typing Pause --> F[CornerCue Accepted]
