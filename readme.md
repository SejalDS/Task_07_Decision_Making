# Task 07 – Ethical Implications of Decision Making  
Syracuse Women’s Lacrosse 2024 – Stakeholder Report  

This repository contains the deliverables for **Task 07**, which builds on Task 05 (LLM descriptive analysis) and Task 06 (synthetic interview). The goal is to translate prior analysis into a **stakeholder-facing decision report** with emphasis on **ethics, reliability, and process documentation**.  

---

## Title & Purpose  
Provide Syracuse Women’s Lacrosse coaching staff with an ethically sound decision report, identifying whether the team should prioritize **offense or defense** to secure additional wins in the 2025 season.  

---

## Executive Summary  
The 2024 season showcased elite offensive efficiency (**46.8% shot conversion vs. 38.6% for opponents**) and strong possession metrics (team draw control edge **384 vs. 334**). **Emma Tyrrell (92 points)** emerged as the offensive anchor, while **Katelyn Mashewske (234 draw controls)** drove possession. Despite these strengths, defensive shortcomings in close games limited outcomes.  

### Recommendations (Tiered by Risk)  
- **Low Risk (Operational):** Targeted coaching for Emma Tyrrell and other scorers to sustain efficiency.  
- **Medium Risk (Investigatory):** Defensive drills and role adjustments for Natalie Smith (36 ground balls, 36 draws).  
- **High Risk (Strategic):** Potential roster/lineup changes or funding reallocations — requiring HR/legal review.  

Confidence is **moderate**. Descriptive stats were validated, but malformed score data limited outcome-based testing. All AI outputs have been labeled and cross-checked for accuracy.  

---

## Background & Decision Question  
**Stakeholders:** Syracuse Women’s Lacrosse coaching staff and athletic director.  
**Decision:** Should the team emphasize offense or defense to secure at least two more wins in the coming season?  
**Risk Level:** Medium (team performance, not health/safety).  

---

## Data & Methods  
- **Dataset provenance:** SU athletics stats (2024 season). Limitation: malformed `Score` column prevented scoring–win correlation analysis.  
- **LLM prompts:** See `Task05/prompts.md`.  
- **Transcript:** Synthetic interview in `Task06/transcript_2024.txt`.  
- **Process notes:** Audio generation and ethical labeling documented in `Task06/README_process_2024.md`.  

---

## Findings  
- **Offense efficiency:** 46.8% vs. 38.6% opponent average.  
- **Key contributors:**  
  - Emma Tyrrell (92 points).  
  - Katelyn Mashewske (234 draw controls).  
  - Natalie Smith (defensive versatility: 36 GB, 36 DC).  
- **Possession advantage:** 384 vs. 334 draw controls.  
- **Weakness:** Defensive lapses in close-game scenarios.  

---

## Uncertainty & Validation  
- Descriptive checks confirm efficiency and possession advantages.  
- Malformed score data limited certain strategy validations.  
- Sanity checks performed; results align with interview narrative.  

---

## Bias & Fairness  
- Representation skewed toward players with offensive stats.  
- AI-generated narrative validated manually; labeled clearly.  
- Avoided over-reliance on LLM outputs without cross-checks.  

---

## Recommendations (Tiered)  
- **Low risk:** Offensive coaching (Emma Tyrrell).  
- **Medium risk:** Defensive drills & role adjustments (Natalie Smith).  
- **High risk:** Roster/lineup changes — HR/legal oversight required.  

---

## Ethical / Legal Considerations  
- All AI-generated outputs labeled clearly.  
- No impersonation of real individuals in synthetic audio.  
- Fairness emphasized in player evaluation.  
- High-stakes changes require compliance review.  

---

## Next Steps & Validation Plan  
1. Compute confidence intervals (e.g., bootstrap on scoring efficiency).  
2. Correct malformed score column to enable outcome testing.  
3. Expand fairness checks (defensive/non-scoring players).  
4. Run controlled scrimmages to test defensive role changes.  

---

## Appendices  
- **LLM Prompts:** `Task05/prompts.md`  
- **Transcript:** `Task06/transcript_2024.txt`  
- **Audio:** `Task06/deepfake_interview_2024.mp3`  
- **Process Documentation:** `Task06/README_process_2024.md`  

