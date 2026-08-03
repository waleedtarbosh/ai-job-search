@AGENTS.md
<!-- Gemini CLI config — imports AGENTS.md -->

# Gemini / Antigravity Quickstart Guide

Welcome to the AI Job Search workspace! This repository is fully compatible with Google Gemini and Antigravity IDE.
To get started with your automated job search, follow these exact steps in your chat:

### 1. Prerequisite: Install LaTeX
If you want Gemini to automatically generate PDF files on your local machine, you must install a LaTeX compiler first:
- **Windows**: Install [MiKTeX](https://miktex.org/download) (ensure you select "Always install missing packages on-the-fly" during setup).
- **Mac**: Install MacTeX (`brew install mactex`).
- **Linux**: Install TeX Live (`sudo apt-get install texlive-full`).

*(Note: If you skip this, Gemini will still generate `.tex` source files which you can manually compile online via Overleaf).*

### 2. Initial Setup (Profile Generation)
Start your agent in this directory and run the setup command to populate your candidate profile:
> *"Run the `setup` command from `.claude/commands/`"*

Gemini will ask you a few questions or read your existing CV from the `documents/` folder to populate your candidate profile in `.claude/skills/job-application-assistant/01-candidate-profile.md` with your personal details.

### 3. Find a Job (Scraping)
To automatically search for live job postings that match your newly created profile:
> *"Run the `scrape` command from `.claude/commands/`"*

### 4. Apply for a Job (Tailored CV & Cover Letter)
When you have a link to a job you want to apply for, use this command to evaluate the fit and generate a tailored CV and Cover Letter:
> *"Run the `apply` command from `.claude/commands/` for this link: [insert_job_url_here]"*

If you installed LaTeX in Step 1, you will instantly find ready-to-send PDF files in your `cv/` and `cover_letters/` folders!