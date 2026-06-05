# ResumeIQ_AI – ATS Resume Analyzer & Scorer

## Overview

ResumeIQ_AI is an AI-powered ATS (Applicant Tracking System) Resume Analyzer designed to help job seekers optimize their resumes for specific job descriptions. The system evaluates resume quality, measures compatibility with job requirements, and provides actionable recommendations to improve ATS performance and increase interview opportunities.

Built using FastAPI, Streamlit, NLP techniques, and Large Language Models (LLMs), the platform delivers intelligent resume analysis with detailed scoring and personalized feedback.


## Features

### Resume Parsing & Analysis

* Upload resumes in PDF, DOC, or DOCX format.
* Extracts skills, education, experience, and key information automatically.
* Supports multiple resume formats.

### Job Description Matching

* Compare resumes against target job descriptions.
* Semantic similarity matching using advanced NLP models.
* Identify missing keywords and required skills.

### ATS Score Generation

* Overall ATS compatibility score.
* Category-wise evaluation:

  * Keyword Optimization
  * Skills Match
  * Content Quality
  * Resume Formatting
  * ATS Compatibility

### AI-Powered Suggestions

* Personalized recommendations generated using LLMs.
* Improve resume content, structure, and keyword relevance.
* Suggestions tailored to the target job role.

### User Authentication

* Secure Email/Password Authentication.
* Google OAuth Login Integration.
* User-specific analysis history.

### Analysis History

* Store previous resume evaluations.
* Track improvements over time.
* Access past reports anytime.

### PDF Report Export

* Download professional ATS analysis reports.
* Share reports with mentors, recruiters, or career coaches.



## Technology Stack

### Frontend

* Streamlit

### Backend

* FastAPI
* Python

### Natural Language Processing

* spaCy (en_core_web_md)
* Sentence Transformers (all-MiniLM-L6-v2)

### Artificial Intelligence

* Groq API
* Llama 3 Models

### Authentication & Database

* Supabase
* Email/Password Authentication
* Google OAuth

### Report Generation

* Jinja2
* WeasyPrint


## How It Works

1. Upload a resume (PDF, DOC, DOCX).
2. Paste the target job description.
3. Resume content is extracted and analyzed.
4. NLP models identify skills, keywords, and experience.
5. Semantic similarity matching compares the resume with the job description.
6. ATS score is calculated.
7. AI generates personalized recommendations.
8. Results are displayed through an interactive dashboard.
9. Users can export reports and save analysis history.


## Installation

### Clone Repository

```bash
git clone <repository-url>
cd ResumeIQ_AI
```

### Create Virtual Environment

```bash
python -m venv venv
```

### Activate Environment

Windows:

```bash
venv\Scripts\activate
```

Linux/Mac:

```bash
source venv/bin/activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
python -m spacy download en_core_web_md
```

---

## Environment Variables

Create a `.env` file and configure:

```env
SUPABASE_URL=
SUPABASE_KEY=
SUPABASE_ANON_KEY=
GROQ_API_KEY=
```

---

## Run Backend

```bash
uvicorn backend.main:app --reload --host 0.0.0.0 --port 8000
```

Backend URL:

```text
http://localhost:8000
```


## Run Frontend

```bash
streamlit run frontend/streamlit_app.py
```

Frontend URL:

```text
http://localhost:8501
```


## Security Notes

* Never commit `.env` files.
* Never expose API keys publicly.
* Keep Supabase service-role keys secure.
* Store secrets in environment variables.



## Author

**Vikki Kumar**

## License

This project is licensed under the MIT License.
