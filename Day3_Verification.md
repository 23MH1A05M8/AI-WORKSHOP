# Day 3 — Lab 3A: Verification Chain
**Name:** HADASSA KUNISETTY
**Date:** 11-06-2025
**Topic:** Indian Campus Placement Statistics 2025

---

## Step 1 — AI-Generated Claims (via Gemini)

The following 5 claims were generated using this prompt in Gemini:
> *"List 5 specific statistics about Indian campus placement in 2025–2026. For each: state the number, the year, and the source organisation. Format as a numbered list."*

| # | Claim as stated by Gemini |
|---|--------------------------|
| 1 | The average B.Tech placement package in Indian engineering colleges in 2025 was ₹6.2 LPA (NASSCOM). |
| 2 | 78% of Tier-1 college students received at least one placement offer in 2025 (AICTE Annual Report). |
| 3 | TCS hired approximately 40,000 freshers in FY2025 (TCS Annual Report). |
| 4 | The median placement package at IITs in 2025 was ₹18.5 LPA (India Skills Report 2025). |
| 5 | Engineering graduates in India had an employability rate of 71.5% in 2025 (India Skills Report 2025 / Wheebox). |

---

## Step 2 — Perplexity Cross-Check

Each claim was submitted to Perplexity with the prompt:
> *"Verify: '[claim]'. Cite 2 primary sources."*

| # | Perplexity Response Summary | URLs Returned |
|---|----------------------------|---------------|
| 1 | Perplexity returned generic salary aggregator pages; could not confirm ₹6.2 LPA as a NASSCOM figure. Suggested the number may come from internal surveys. | https://nasscom.in/knowledge-center/publications/ , https://collegedunia.com (aggregator) |
| 2 | Perplexity could not locate a 2025 AICTE Annual Report with the specific "78%" figure. Returned NIRF and AICTE landing pages, not specific report pages. | https://www.aicte-india.org , https://www.nirfindia.org |
| 3 | Perplexity confirmed TCS has announced ~40,000 fresher hiring plans for FY26, citing Economic Times (Sept 2025) quoting TCS CHRO Milind Lakkad. Note: FY26 ≠ FY25. | https://economictimes.indiatimes.com , https://tcs.com/careers |
| 4 | Perplexity returned multiple IIT-specific placement pages showing median packages ranging ₹17–₹26 LPA. Could not find a single "IIT median" of ₹18.5 LPA in the India Skills Report. | https://www.careers360.com/university/iit-delhi , https://wheebox.com |
| 5 | Perplexity confirmed the 71.5% engineering employability figure. Multiple sources (IBEF, Business Standard, GS Score) cite the India Skills Report 2025 by Wheebox/CII/AICTE. | https://www.ibef.org/news/55-indian-grads-to-be-globally-employable-in-2025 , https://www.business-standard.com |

> **Note:** Perplexity is also fallible. All URLs above were opened and read manually in Step 3.

---

## Step 3 — Primary Source Verification

| # | Primary Source Opened | What the Source Actually Says | Match with Claim? |
|---|----------------------|-------------------------------|-------------------|
| 1 | https://nasscom.in/knowledge-center/publications/india-technology-industry-compensation-benchmarking-survey-findings-1 | NASSCOM's 2025 Compensation Benchmarking report discusses pay premiums for AI/ML and DevOps roles and notes that campus hiring skill requirements have shifted. It does **not** publish a figure of ₹6.2 LPA as an all-India average B.Tech package. The report focuses on the tech industry specifically, not all engineering colleges. | **FALSE / NO PRIMARY SOURCE FOUND** — The number ₹6.2 LPA as a NASSCOM-cited all-India average does not appear in the actual NASSCOM publication. |
| 2 | https://www.aicte-india.org (Annual Report section) | The AICTE website does not publish a downloadable 2025 Annual Report with a "78% placement offer rate for Tier-1 colleges" figure. The NIRF 2025 data covers individual institution-level placement rates which vary widely. No single "78% Tier-1" headline statistic exists in AICTE documentation. | **NO PRIMARY SOURCE FOUND** — The figure is unverifiable; the source does not contain this claim. |
| 3 | https://tcs.com/investors (Annual Report) / Economic Times report | TCS announced hiring of 40,000+ freshers for **FY2026** (April 2025–March 2026), not FY2025. In FY2025, TCS actually reduced fresher hiring due to IT demand slowdown. The TCS CHRO statement was made in September 2025 referring to FY26 plans. | **PARTIAL** — The number (40,000) is approximately correct, but the year is wrong. Gemini said "FY2025"; the actual announcement is for FY2026. |
| 4 | https://www.careers360.com/university/iit-delhi/placement , https://collegedunia.com IIT Madras placement page | IIT-specific median packages in 2025 vary significantly: IIT Delhi UG 4-year median = ₹20 LPA (NIRF 2026), IIT Madras UG median = ₹17.78–₹19.6 LPA, IIT Bombay UG median ≈ ₹19.6 LPA. The India Skills Report 2025 (Wheebox) does **not** publish an "IIT median package of ₹18.5 LPA" — it covers employability rates, not IIT-specific salary figures. | **FALSE** — The source cited (India Skills Report) does not contain IIT median salary data. The number ₹18.5 LPA is not from the stated source. Actual IIT medians are higher and institution-specific. |
| 5 | https://www.ibef.org/news/55-indian-grads-to-be-globally-employable-in-2025-says-cii-report , https://www.business-standard.com/india-news/employability-among-indian-graduates-improves-to-54-81-wheebox-report | The India Skills Report 2025 (Wheebox/CII/AICTE), based on 6.5 lakh candidates, confirms engineering graduate employability at **71.5%**. This figure is consistent across multiple reputable sources (IBEF, Business Standard, GS Score all citing the same report). | **VERIFIED** — The figure, year, and source organisation all match the primary source. |

---

## Step 4 — Verdict Summary

| # | Claim | Verdict |
|---|-------|---------|
| 1 | Avg B.Tech package ₹6.2 LPA in 2025 (NASSCOM) | **FALSE / NO PRIMARY SOURCE FOUND** |
| 2 | 78% of Tier-1 students got placement offers in 2025 (AICTE) | **NO PRIMARY SOURCE FOUND** |
| 3 | TCS hired ~40,000 freshers in FY2025 (TCS Annual Report) | **PARTIAL** — Number is approximately right; year is wrong (FY2026, not FY2025) |
| 4 | IIT median package ₹18.5 LPA in 2025 (India Skills Report) | **FALSE** — Source cited does not contain this figure |
| 5 | Engineering graduate employability 71.5% in 2025 (India Skills Report / Wheebox) | **VERIFIED** |

> **Result:** 1 VERIFIED, 1 PARTIAL, 2 NO PRIMARY SOURCE FOUND, 1 FALSE  
> Requirement met: at least 1 PARTIAL or FALSE verdict ✅

---

## Step 5 — Reflection Paragraph

The claim that looked most authoritative but was actually the weakest was **Claim #4**: *"The median placement package at IITs in 2025 was ₹18.5 LPA (India Skills Report 2025)."* Gemini cited the India Skills Report confidently — it's a well-known, credible, annually published report by Wheebox in collaboration with AICTE and CII. Perplexity initially seemed to confirm this by returning the Wheebox URL alongside IIT placement pages. But when I opened the actual India Skills Report 2025 source, I found that the report covers **graduate employability rates** across degree types — it does not publish IIT-specific median salary figures at all. The ₹18.5 LPA number appears to be a plausible-sounding invention: the real IIT medians in 2025 range from ₹17.78 LPA (IIT Madras) to ₹20 LPA (IIT Delhi), depending on the institution. No single number applies to "all IITs," and the India Skills Report is not the source for any of them. The lesson: **confidence does not equal correctness.** The more authoritative and specific a claim sounds — a named report, a precise number, a respected organisation — the more carefully it must be verified against the actual source document. The verification step belongs to the human, every time.

---

