# Hipages Take‑Home Test — Data Analyst (Kevin Abraham)

This repository contains my submission for the hipages Data Analyst take‑home.  
It includes:
- (1) SQL solutions for the messaging platform schema
- (2) Exploratory Data Analysis (EDA) on the provided jobs dataset, with final visuals published to Tableau Public.

- **Live Dashboard:** [https://public.tableau.com](https://public.tableau.com/views/JobAcceptanceDrivers-CaseStudybyKevinA/Final?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
- **Live Py Notebook (colab):**  [https://colab.research.google.com](https://colab.research.google.com/drive/15BuH8CWMDUHJkDEU8F5dNSoVY73bj8CN?usp=sharing)  
- **Offline Notebook:** `Take_Home_Test_from_HiPages_Kevin_Abraham.ipynb`  
- **Offline Tableau Workbook:** `tableau_workbook.twb`  
- **Brief (PDF):** `Take Home Task - Data Analyst.docx.pdf`

---

## Contents
- `/part_1/Take_Home_Test_from_HiPages_Kevin_Abraham.ipynb` — SQL answers
- `/part_2/tableau_workbook.twb` — Tableu workbook + EDA walkthrough
- `Take Home Task - Data Analyst.docx.pdf` — requirements (from hipages)
- `final.pdf` — dashboard export (summary of key findings)

---

## Task 1 — SQL Programming (Messaging Platform)
Schema: `Users`, `Threads`, `Messages`.

Queries delivered:
1. **Names + count of messages sent by each user**  
   - Join `Messages` to `users` on `UserIDSender` group by name.
2. **Total messages by weekday**  
   - Extract weekday from `messages.DateSent`.
3. **Most recent unanswered message per thread**  
   - For each thread, find the latest message with no later reply.
4. **Conversation with the most messages (full history)**  
   - Identify thread with max message count. return user + message text ordered chronologically.

Notes:
- Queries (standard SQL using SQL-Lite)
- Edge cases considered: ties for max thread.

---

## Task 2 — EDA (Jobs Dataset)
Goal: Understand drivers of job acceptance and communicate insights.

### Steps
- **Data prep:** basic cleaning, outlier handling for impressions, create helper features (e.g AM/PM)
- **Exploration:**  
  - Acceptance vs **time-of-day**  
  - Acceptance vs **category** and **supply** (`number_of_tradies`)  
  - Acceptance vs **impressions** (IPT = `number_of_impressions / number_of_tradies`)
- **Visualisation:** Published to Tableau Public (link above).

### Key Insights (see dashboard)
- **Timing:** Acceptance lifts in **early afternoon (~1–4 PM)**. morning below baseline.  
- **Supply:** Categories with more supply have higher acceptance. low supply categories underperform.  
- **Views (IPT):** Acceptance increases with impressions, low impressions jobs are also lower performers.

### Recommendations
- **Schedule:** Queue first/followup notifications to be in **1–4 PM**.  
- **Supply:** Grow supply or widen radius for low supply categories.  
- **Views:** Increase IPT for underperforming categories.
- **Validation:** A/B tests as explained in the EDA.

### Caveats
- **Visual Correlations:** All of this is weak visual correlation, deeper analysis is required to verify results with hard numbers. 
- **Data cleaned:** There was some noise in this dataset that was cleaned. Same analysis would need to be done on alternative datasets e.g diff date range to see if these outcomes still hold up
- **Outliers:** Outliers were removed but more work is needed to verify threshold for small sample groups. Would be done during a full deep dive analysis

---

## How to Run
- Open the notebook in Jupyter/Colab.
- Python 3, pip install core libs: `pandas`, `numpy`, `pandasql` or just run in colab.  
- Use datasets provided in this git.

---

## Notes & Assumptions
- Times assumed to be local.
- Acceptance is treated as the primary target variable.

---

## Author
**Kevin Abraham**  
- Tableau Public: https://public.tableau.com/views/JobAcceptanceDrivers-CaseStudybyKevinA/Final?:language=en-US&publish=yes&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
- GitHub: https://github.com/imkevinabraham  