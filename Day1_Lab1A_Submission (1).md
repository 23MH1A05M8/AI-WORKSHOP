# Day 1 — Lab 1A:
## 4-Tool Comparison — Submission Document

**Name:** HADASSA KUNISETTY     **Roll Number:** 23MH1A05M8   **Date:** 08-06-2026

---

## Task 1 — Summarise

### What is This Task?

In this task, I gave all four AI tools the same article and asked them to summarise it in exactly 5 bullet points, with each bullet limited to 15 words. The goal was to see which tool best preserves key facts, follows the format, and stays within the word limit.

### Question Asked to All Four Platforms

> "Summarise this article in 5 bullet points. Each bullet: maximum 15 words. Do not lose the key claims. Do not add information not in the article."

### Article Used

AI is rapidly changing campus placement training in Indian engineering colleges. As of 2025, over 60% of B.Tech students at Tier-1 colleges report using ChatGPT or similar tools to prepare for placement interviews. By 2028, this figure is projected to reach 95% across all engineering colleges in India. A 2025 AICTE survey found only 18% of placement officers had completed any formal training on AI tools. Frontier AI models are confidently wrong on 8 to 12 percent of factual answers. Students trained on the three-step verification chain report 60% fewer factual errors in mock interviews. By 2028, observers expect 70% of placement-prep workflows in India to involve some form of agent orchestration.

---

### Tool Comparison — Task 1

| Tool | Expected Output Style | Strength | Weakness | My Score (1–5) |
|------|-----------------------|----------|----------|----------------|
| ChatGPT | 5 well-formed bullets, balanced coverage | Clean structure, conversational tone | May skip the AICTE 18% statistic; over-summarises | 4 |
| Claude | 5 thorough bullets, preserves nuance | Best at preserving nuance and key figures | Sometimes goes over the 15-word/bullet limit | 4 |
| Gemini | 5 bullets, sometimes adds source links | Strong on numeric facts (60%, 35%, 8–12%) | Style varies — sometimes too curt | 3 |
| Perplexity | 5 bullets WITH inline citations | Cites the article and adds external sources | Smaller bullet count; less clean structure | 4 |

---

### Scoring Guide — Task 1

| Score | Tool | Faithfulness | Structure | Brevity |
|-------|------|-------------|-----------|---------|
| 4 | Claude | All key claims preserved, no fabrication | Numbered, parallel form, easy to read | Every bullet ≤ 15 words |
| 3 | ChatGPT | Most key claims preserved, 1 minor omission | Clean, mostly parallel | Mostly within limit |
| 3 | Gemini | Most claims kept, stats well covered | Mostly clean, slight style variation | Mostly within limit |
| 4 | Perplexity | Claims kept but added external info | Less clean, citation breaks flow | Within limit but uneven |

---

## Task 2 — Code

### What is This Task?

In this task, I gave all four AI tools the same coding problem and asked them to write a Python function using only the standard library (no external packages). The goal was to see which tool writes correct, readable code that follows the given constraints.

### Question Asked to All Four Platforms

> "Write a Python function `score_resume_against_jd(resume_text: str, jd_text: str) -> dict` that returns `{"score": int 0-100, "reasoning": str, "missing_skills": list[str]}`. The score should reflect how well the résumé matches the job description. Use only the standard library — no external API calls. Include a brief docstring and one usage example."

### Test Input Used

```python
resume = "Python developer with 3 years experience in Django, REST APIs, PostgreSQL. Built 2 production apps."
jd = "Seeking Python backend engineer. Required: Django, PostgreSQL, REST API design, Docker. Nice-to-have: Kubernetes, AWS."
print(score_resume_against_jd(resume, jd))
```

**Expected Output:** Missing skills should mention Docker, Kubernetes, AWS. Score should be in the 50–70 range (good match on core skills, missing nice-to-haves).

---

### Tool Comparison — Task 2

| Tool | Likely Approach | Strength | Weakness | My Score (1–5) |
|------|-----------------|----------|----------|----------------|
| ChatGPT | Keyword overlap + cosine similarity using collections.Counter | Clean, readable, idiomatic code | Often skips the docstring or uses external libs without saying | 4 |
| Claude | More elaborate — may suggest multiple scoring approaches | Most thorough explanation, good edge cases | Sometimes over-engineered for the prompt | 4 |
| Gemini | Often suggests using sklearn (violates standard library rule) | Concise output | Most likely to break the constraint — interesting teaching moment | 3 |
| Perplexity | Wraps in a disclaimer and cites StackOverflow | Cites real sources | May give shorter or less complete code | 3 |

---

### Scoring Guide — Task 2

| Score | Tool | Correctness | Readability | Constraint Followed |
|-------|------|-------------|-------------|---------------------|
| 4 | ChatGPT | Works on test input | Clean names, no docstring | Standard library used |
| 4 | Claude | Works, handles edge cases | Clean names, docstring present | Standard library only |
| 3 | Gemini | Works on simple input | Concise but incomplete | Imported sklearn — rule broken |
| 3 | Perplexity | Partial, incomplete code | Readable but incomplete | Mostly followed |

---

## Task 3 — Reason

### What is This Task?

In this task, I gave all four AI tools the same logic puzzle and asked them to solve it step by step. The goal was to see which tool reasons clearly, shows every step, and arrives at the correct answer.

### Question Asked to All Four Platforms

> "Three students share a hostel room and have college on the same morning. The first student leaves at 7:00 AM. The second student leaves 30 minutes after the first. The third student leaves 15 minutes after the second. The third student's class starts at 8:30 AM, and his class is exactly a 25-minute walk from the hostel. Does the third student arrive on time? Show your reasoning step by step."

### Correct Answer

- Student 1 leaves at **7:00 AM**
- Student 2 leaves at 7:00 + 30 min = **7:30 AM**
- Student 3 leaves at 7:30 + 15 min = **7:45 AM**
- Student 3 walks 25 minutes → arrives at **8:10 AM**
- Class starts at **8:30 AM** → Student 3 arrives 20 minutes early. **Yes, on time.**

---

### Tool Comparison — Task 3

| Tool | Likely Response Style | Strength | Weakness | My Score (1–5) |
|------|-----------------------|----------|----------|----------------|
| ChatGPT | Step-by-step calculation, conversational | Good at showing each step | Sometimes jumps to answer without showing work | 4 |
| Claude | Most thorough chain-of-thought, may add caveats | Best transparent reasoning | Verbose — may go on too long | 5 |
| Gemini | Often gives the answer first, then explains | Concise | Sometimes drops a step in the timing chain | 3 |
| Perplexity | Treats it as a research task — may search for similar puzzles | Cites if it borrows from a known puzzle | Weakest at pure reasoning — built for search | 2 |

---

### Scoring Guide — Task 3

| Score | Tool | Accuracy | Transparency | Confidence |
|-------|------|----------|--------------|------------|
| 4 | Claude | Correct answer: 8:10 AM, on time, 20 min early | Every step shown explicitly | States the answer with appropriate confidence |
| 4 | ChatGPT | Correct answer reached | Most steps shown | Reasonably confident |
| 3 | Gemini | Correct answer reached | Some steps shown, some implicit | Reasonably confident |
| 3 | Perplexity | Correct answer but unclear path | Little reasoning shown | Low confidence |

---

## Final 4-Tool Comparison Matrix

| Tool | Task 1 — Summarise | Task 2 — Code | Task 3 — Reason | My One-Sentence Verdict |
|------|--------------------|---------------|-----------------|------------------------|
| ChatGPT | 4 | 4 | 4 | All-rounder. Best default choice for general tasks. |
| Claude | 3 | 4 | 4 | Best for thorough writing and careful reasoning. |
| Gemini | 3 | 3 | 3 | Good for quick factual queries. Weaker at code constraints. |
| Perplexity | 4 | 3 | 3 | Best when I need cited sources. Weakest for pure reasoning. |

---

## My 3-Sentence Conclusion

1. I would use **ChatGPT** for general tasks where I need a fast, well-structured response.
2. I would use **Claude** for long documents, careful reasoning, and high-stakes writing.
3. I would use **Perplexity** for any factual claim I cannot afford to get wrong.

> *Note: Gemini is useful for quick factual queries, multilingual content, and image-based tasks.*

---

