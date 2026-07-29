@AGENTS.md
<!-- OpenCode config — imports AGENTS.md -->

> **🤖 OPENCODE SYSTEM INSTRUCTION:**
> You are operating in the `ai-job-search` workspace. **Do not invent workflows.**
> Your single source of truth for all commands and execution logic is located in `AGENTS.md` and the `.claude/commands/` directory. 
> Whenever the user triggers a mode (setup, scrape, apply, etc.), you must strictly read and execute the instructions defined in those core files to prevent workflow drift.


# OpenCode Quickstart Guide

Welcome to the AI Job Search workspace! This repository is fully compatible with OpenCode. 
To get started with your automated job search, follow these exact steps in your OpenCode chat:

### 1. Prerequisite: Install LaTeX
If you want OpenCode to automatically generate PDF files on your local machine, you must install a LaTeX compiler first:
- **Windows**: Install [MiKTeX](https://miktex.org/download) (ensure you select "Always install missing packages on-the-fly" during setup).
- **Mac**: Install MacTeX (`brew install mactex`).
- **Linux**: Install TeX Live (`sudo apt-get install texlive-full`).

*(Note: If you skip this, OpenCode will still generate `.tex` source files which you can manually compile online via Overleaf).*

### 2. Initial Setup (Profile Generation)
Start OpenCode in this directory and run the setup command to populate your candidate profile:
> *"Run the `setup` mode using the `job-search` skill"*

*(Or use the quick command: `/job-search mode="setup"`)*

OpenCode will ask you a few questions or read your existing CV from the `documents/` folder to populate the `config/` files with your personal details.

### 3. Find a Job (Scraping)
To automatically search for live job postings that match your newly created profile:
> *"Run the `scrape` mode using the `job-search` skill"*

### 4. Apply for a Job (Tailored CV & Cover Letter)
When you have a link to a job you want to apply for, use this command to evaluate the fit and generate a tailored CV and Cover Letter:
> *"Use the `job-search` skill to run the `apply` mode for this link: [insert_job_url_here]"*

If you installed LaTeX in Step 1, you will instantly find ready-to-send PDF files in your `cv/` and `cover_letters/` folders!
