@AGENTS.md
<!-- Codex config — imports AGENTS.md -->

# Codex Quickstart Guide

Welcome to the AI Job Search workspace! This repository is fully compatible with Codex.
To get started with your automated job search, follow these exact steps in your chat:

### 1. Prerequisite: Install LaTeX
If you want Codex to automatically generate PDF files on your local machine, you must install a LaTeX compiler first:
- **Windows**: Install [MiKTeX](https://miktex.org/download) (ensure you select "Always install missing packages on-the-fly" during setup).
- **Mac**: Install MacTeX (`brew install mactex`).
- **Linux**: Install TeX Live (`sudo apt-get install texlive-full`).

*(Note: If you skip this, Codex will still generate `.tex` source files which you can manually compile online via Overleaf).*

### 2. Initial Setup (Profile Generation)
Start your agent in this directory and run the setup command to populate your candidate profile:
> *"Run the `setup` mode using the `job-search` skill"*

Codex will ask you a few questions or read your existing CV from the `documents/` folder to populate the `config/` files with your personal details.

### 3. Find a Job (Scraping)
To automatically search for live job postings that match your newly created profile:
> *"Run the `scrape` mode using the `job-search` skill"*

### 4. Apply for a Job (Tailored CV & Cover Letter)
When you have a link to a job you want to apply for, use this command to evaluate the fit and generate a tailored CV and Cover Letter:
> *"Use the `job-search` skill to run the `apply` mode for this link: [insert_job_url_here]"*

If you installed LaTeX in Step 1, you will instantly find ready-to-send PDF files in your `cv/` and `cover_letters/` folders!
