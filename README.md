# Automated CV Screening & HR Pipeline (n8n & GPT-4o)

This repository contains the n8n workflow definition for an **Automated Candidate Screening and HR Pipeline**. It automates candidate application collection, resume text extraction, AI grading, and database logging.

## Key Technical Features
* **n8n Form Trigger Ingestion:** Captures form submissions (Name, Email, Years of Experience, and CV PDF uploads).
* **Google Drive API Handler:** Uploads CV files to a secure Drive folder using clean naming conventions.
* **PDF Text Extraction:** Parses binary PDF CV data into raw text strings.
* **GPT-4o Scoring Engine:** Evaluates candidate CVs against job descriptions using a weighted formula: Technical Skills (40%) + Experience (30%) + Industry Relevance (20%) + Additional Qualifications (10%).
* **Gatekeeper Routing:** Filters out candidates with job title mismatches. Scores above 0.6 are logged to the Interview Sheets; lower scores are routed to Rejections.

## Workflows Included
1. `automated-cv-screening-hr-pipeline.json` (Full recruitment screening and logging pipeline)

## Deployment Instructions
1. Import `automated-cv-screening-hr-pipeline.json` into n8n.
2. Configure credentials for Google Drive and Google Sheets.
3. Set the form fields and link to your target Google Sheet with 'Accepted' and 'Rejected' sheets.
4. Add your OpenAI API Key inside the LangChain Agent nodes.
