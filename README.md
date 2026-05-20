# AI-Powered Job Application Automation Pipeline

An end-to-end automated pipeline built on **Make.com** that dynamically analyzes job descriptions, matches them against a candidate's master CV using an advanced multi-agent LLM chain (inspired by LangChain methodology), and delivers tailored applications directly to your inbox.

---

## 📌 Architecture & Workflow

The system bypasses traditional, time-consuming manual application tailoring by executing a highly optimized, trigger-based data pipeline.

### Full Pipeline Overview

<img width="1365" height="674" alt="image" src="https://github.com/user-attachments/assets/67eee375-213b-4602-b063-4d0a929bad76" />

## 🛠️ Detailed Component Breakdown

### 1. Data Intake Layer (Google Workspace)
The pipeline begins with a centralized intake form to capture target job profiles.

<img width="1365" height="676" alt="image" src="https://github.com/user-attachments/assets/a6e49c5b-8803-488c-9dd1-7b77b460c463" />
<img width="1365" height="677" alt="image" src="https://github.com/user-attachments/assets/a8e497c4-2491-42ea-97a7-2e16892bff20" />
<img width="1365" height="679" alt="image" src="https://github.com/user-attachments/assets/671864b8-7a79-4b0a-a813-d3879a63367f" />

### 2. Document Source (Master CV)
A plain-text structured Google Doc serves as the single source of truth for the candidate's professional profile.

<img width="1364" height="680" alt="image" src="https://github.com/user-attachments/assets/43f04f66-c581-4d04-8979-e96a6552cd43" />

---

## 🤖 Deep Dive: Multi-Agent AI Chain (LangChain Paradigm)

Instead of a generic all-in-one prompt, this project utilizes a modular chain architecture where specialized agents pass contextual data downstream to maximize output quality.

| Agent / Module | System Prompt Architecture | Input / Context Data |
| :--- | :--- | :--- |
| **1. Job Analyzer** | `"You are a job posting analyst. Extract the top 5 required skills, experience level, company culture indicators, and key responsibilities. Respond in structured format."` | Job Description & Requirements from Google Sheets |
| **2. Skill Matcher** | `"You are a career advisor. Given a job analysis and a candidate's CV, identify matching skills, skill gaps, and which CV sections to emphasize."` | Output of Job Analyzer + Master CV content from Google Docs |
| **3. Document Generator** | `"You are a professional writer. Using the skill match analysis, generate a personalized cover letter and a list of specific CV adjustments."` | Output of Skill Matcher + Company Name & Position Title |

<img width="1365" height="680" alt="image" src="https://github.com/user-attachments/assets/02962c7d-9c43-4f9a-9917-b3bec644bda8" />
<img width="1365" height="676" alt="image" src="https://github.com/user-attachments/assets/f8fd3c07-376a-4c82-be35-393075ca5f70" />

### 📈 Quality Improvements Over Single-Prompt AI:
1. **Hyper-Personalization:** The final *Document Generator* focuses strictly on the extracted cultural indicators and company identity processed by the *Job Analyzer*, rather than injecting generic corporate buzzwords.
2. **Granular Skill Alignment:** The *Skill Matcher* pinpoints precise technical intersections and uncovers critical skill gaps between the master CV and the job description, ensuring no vital industry keywords are omitted.
3. **Actionable CV Adjustments:** Instead of rewriting the entire CV from scratch or fabricating experiences, the pipeline isolates and generates strategic, fact-accurate layout adjustments and phrasing emphasis based on quantified role analysis.

---

## 📬 Notification Layer: Dynamic Email Routing

Once both content-generation pipelines finish execution, a dedicated Gmail node compiles the outputs into an email layout. The subject line and header sections update dynamically according to the role and corporate entity.

| Subject & Recipient Structure | Email Content Payload Mapping |

<img width="1365" height="682" alt="image" src="https://github.com/user-attachments/assets/6242c13c-ee91-4952-bce0-bda0f6352174" />
<img width="1365" height="682" alt="image" src="https://github.com/user-attachments/assets/560fd266-4efc-4bf2-8141-378aaaa0830b" />

---

## 🚀 Execution & Output Verification

### Successful Pipeline Run Execution
Below is the execution logs from the active pipeline tracking operation routing directly to the inbox destination.

<img width="1365" height="678" alt="image" src="https://github.com/user-attachments/assets/eaa559e7-bd7d-44a7-8b16-e3aeb5e3f21a" />

### Final Delivered Output
The final automated delivery safely transmits the compiled, completely formatted professional application kit instantly.

<img width="1365" height="680" alt="image" src="https://github.com/user-attachments/assets/1f70df90-d10c-45c6-b694-6534538cbb52" />
<img width="1365" height="679" alt="image" src="https://github.com/user-attachments/assets/e625b19c-375c-47c9-95fd-5cfc602c44c4" />

---

## 💻 Tech Stack

* **Orchestration & Workflow Automation:** Make.com (Formerly Integromat)
* **LLM Gateway Router:** OpenRouter API (`StepFun: Step 3.5 Flash (free)`)
* **Data Integration Stack:** Google Workspace Ecosystem (Forms, Sheets, Docs, Gmail)

---

## 🏁 How to Replicate

1. **Clone Layouts:** Set up a Google Form capturing *Company, Role, Job Description, and Requirements*, then route responses to a Google Sheet.
2. **Load Master CV:** Place your plain-text, markdown-friendly CV inside a Google Doc.
3. **Import Scenario:** Recreate the sequence using the Make.com visual builder as shown in the workflow diagram.
4. **Connect Accounts:** Authorize Make.com to access your Google Sheet, Docs, and Gmail using the default built-in connections.
5. **Run & Automate:** Click "Run once" to test, then activate the scheduling toggle to transition the workflow into real-time production.
