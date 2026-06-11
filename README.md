
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
```
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
