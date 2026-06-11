
# AI Mentor Bootcamp — HADASSA KUNISETTY

Repo URL - https://github.com/23MH1A05M8/AI-WORKSHOP 

Public portfolio of 12-day AI Trainer Workshop. By Day 12: 6 daily notebooks + capstone Streamlit URL.

## Day 1 — Setup complete

- ✅ Google AI Studio API key provisioned
- ✅ Groq API key provisioned
- ✅ Hello-Gemini call working — see [Day1_Setup.ipynb](Day1_Setup.ipynb)

![Gemini first call](gemini_first_call.png)

- ✅ Hello-Groq call working — see [Day1_Setup_groq.ipynb](Day1_Setup_groq.ipynb)
  
![Groq first call](groq_first_call.png)

- 4-tool comparison matrix from Lab 1A: see screenshot below

  
## Day 2 Lab 2B – JSON Resume Extractor
Objective

Build an AI-powered resume extraction pipeline that converts unstructured resume text into structured JSON using Gemini's Structured Output API and validates the output using Pydantic.

### Technologies Used
  Python
  Google Gemini 2.5 Flash
  Pydantic
  Google Colab
### Implementation
  Defined a structured Resume schema using Pydantic models.
  Configured Gemini Structured Output using response_schema.
  Extracted candidate information from resume text into JSON format.
  Validated model output against the predefined schema.
  Implemented retry logic to repair malformed JSON responses.
  Processed multiple resumes and converted them into structured data objects.
  Added validation for empty input and handled extraction failures gracefully.
### Fields Extracted
  Name
  Email
  Phone Number
  Education Details
  Skills
  Projects
  Experience (Years)
  
![Day2_ResumeExtractor](Day2_ResumeExtractor.png)

![Day2_ResumeExtractorJSON](Day2_ResumeExtractorJSON.png)

## Day4A - Productivity Sprint

**Company:** Amazon (SDET Intern)

### Edit Notes

1. Verified interview process using Amazon careers information and candidate interview experiences.
2. Compensation figures varied across sources; marked as "[verify with official offer letter]".
3. Replaced Gamma's generic cover title with "Build Quality at Scale — Launch Your SDET Career at Amazon".

### Files

* `Day4_Amazon_brief.pdf`
* `Day4_AMAZON_deck.pdf`

### Sources

* Amazon Careers
* Amazon Jobs
* Glassdoor interviews
* GeeksforGeeks interview experiences
* LeetCode discussions
* AmbitionBox
* LinkedIn job postings

# Day 4 — Lab 4B: n8n Daily News Digest

A self-hosted, automated workflow that fetches daily placement and tech news via RSS, processes and summarizes the text using the Groq API, and emails a concise 5-bullet digest every morning.

---

## 🛠️ Tech Stack & Workflow

*   **Host:** Self-hosted via Docker (`docker-compose`)
*   **Automation Engine:** n8n
*   **LLM API:** Groq (`api.groq.com/openai/v1/chat/completions`)
*   **Delivery:** Gmail / SMTP Node

### Workflow Architecture
`Schedule Trigger (7:00 AM IST)` ➔ `RSS Read Node` ➔ `HTTP Request (Groq API)` ➔ `Gmail / SMTP Send Node`

---

## 🚀 Setup & Execution

1.  **Start n8n Instance:**
```bash
    docker compose -f n8n_docker-compose.yml up -d
    ```
2.  **Configure Workflow:** Imported and wired the nodes on `localhost:5678`.
3.  **Prompt Optimization:** Integrated a custom system prompt within the Groq payload to restrict summaries to 5 bullets (≤ 20 words per bullet) focusing on hiring, layoffs, and tech demand.
4.  **Activation:** Set Cron expression to `0 7 * * *` and toggled the workflow to **Active**.

---

## 📦 Deliverables

*   ✅ **Workflow JSON:** [Day4_NewsDigest.json](Day4_NewsDigest.json)
*   ✅ **Status:** Active & Automated

### Verification Screenshot

![Test Email Receipt](n8n.png)
![Test Email Receipt](Day4_daily_digest_test_email-2.png)
