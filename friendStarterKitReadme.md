# resumeBuilderFriendStarterKit

LastUpdated: 2026-02-20

This kit helps you generate tailored resumes fast without rewriting from scratch every time.

## Core idea

1) Put your “truths” into **one master JSON** (yourTruthBank).  
2) For each job, generate a **job-specific JSON** (a subset).  
3) Paste the job-specific JSON into the Resume Builder web app, **Print to PDF**, then apply.

This avoids drift and keeps your resume consistent.

---

## What you need

- The Resume Builder web app link (provided by Grant)
- `dataSchema.json` (provided by Grant)
- Your current resume (PDF or DOCX)

---

## Files you will create

- `yourTruthBank_YYYYMMDD.json`  
  Your master, reusable resume database in JSON.

- `jobSpecificResume_company_role_YYYYMMDD.json`  
  A tailored subset for one job application.

- `resume_company_role_YYYYMMDD.pdf`  
  The final PDF you submit.

---

## Step-by-step workflow

### Step 1 — Convert your resume into a truth bank JSON

In ChatGPT, upload:
- your current resume
- `dataSchema.json`

Then run the prompt in `friendStarterKitPrompts.txt` titled:
**Prompt A: Resume → Truth Bank JSON**

Save the result as:
`yourTruthBank_2026-02-20.json`

Tip: This first version does not need to be perfect. You can improve it over time.

---

### Step 2 — Expand your truth bank safely (optional but recommended)

Use:
**Prompt B: Expand my truth bank safely**

This suggests additional bullets that you can confirm are true.

Important:
- Confirm “yes/no” for each suggestion.
- If you say yes, provide missing details.
- Do not add numbers unless you personally know them.

---

### Step 3 — Create a ChatGPT Project: Job Targeting Agent

Create a new ChatGPT Project named:
**JobTargetingAgent**

Set the Project’s system prompt to the text under:
**System Prompt: Job Targeting Agent** (in `friendStarterKitPrompts.txt`)

Usage for each job:
1) Paste the job description
2) Paste your latest truth bank JSON
3) Copy the output JSON and save as `jobSpecificResume_...json`

---

### Step 4 — Create a ChatGPT Project: Truth Bank Updater

Create another Project named:
**TruthBankUpdater**

Set the Project’s system prompt to:
**System Prompt: Truth Bank Updater** (in `friendStarterKitPrompts.txt`)

Use it to add only confirmed new bullets and keep your truth bank clean.

---

### Step 5 — Generate the final resume PDF

1) Open the Resume Builder web app  
2) Paste `jobSpecificResume_...json` into the JSON box  
3) Click Render  
4) Print → Save as PDF  
5) Apply

---

## Safety rules (keep these)

- Never let ChatGPT invent metrics, tools, dates, titles, or employers.
- If something is missing, it should ask a question instead of guessing.
- Prefer using items marked `verified: true`.
- Keep old copies of your truth bank in case you need to roll back.

---

## Quick troubleshooting

### “It only prints one page”
Your app should hide the editor column and allow pagination in print mode.
If printing still clips, share a screenshot of Print Preview with Grant.

### “The JSON won’t render”
Usually means invalid JSON:
- missing comma
- missing quotes
- extra trailing commas

Try pasting into a JSON validator or re-run Prompt A.

---

## Suggested habits

- Update your truth bank once per week while job searching
- Keep a folder:
  - `/truthBank/`
  - `/jobSpecific/`
  - `/pdf/`
