# AI Job Search: Architecture & Plan 

## Overview
This repository uses a **Universal AI Agent Architecture** (sometimes referred to as the career-ops style). It is designed to ensure that your automated job search workflows work perfectly and identically across any AI framework (OpenCode, Claude Code, Antigravity, Codex, Gemini, etc.) with absolutely **zero logic drift**.

## Core Architectural Pillars

### 1. The Single Source of Truth (`AGENTS.md`)
Instead of locking the candidate's profile into tool-specific files (like `CLAUDE.md`), this architecture relies on a "Thin-Pointer" design. 
- **`AGENTS.md`** is the canonical brain. It holds the overarching rules, directory structure, and the baseline candidate profile.
- Files like `OPENCODE.md`, `CLAUDE.md`, `CODEX.md`, and `GEMINI.md` are just thin wrappers that import or point directly to `@AGENTS.md`. 
- This guarantees that no matter which AI tool you use, it reads the exact same foundational data.

### 2. Universal Workflow Logic (`.claude/commands/`)
Workflow logic (how to evaluate a job, how to scrape, how to apply) is **not** hidden in tool-specific command folders.
- All 12 core commands (e.g., `setup`, `apply`, `interview`, `rank`) are stored as pure markdown instructions in the `/.claude/commands/` directory.
- `.claude/commands/_shared.md` contains strict, universal rules (like the Verification Checklist for CV generation) that apply to every workflow.

### 3. Centralized Reference Data (`.claude/skills/job-application-assistant/`)
All candidate-specific data, methodologies, and templates live in `/.claude/skills/job-application-assistant/`. 
- When the user runs the `setup` mode, the AI parses their raw documents and generates highly structured files like `01-candidate-profile.md` and `04-job-evaluation.md`.
- These files are heavily referenced by the `.claude/commands/` scripts to generate tailored cover letters and CVs.

### 4. Intelligent Routers (`SKILL.md`)
To make the `.claude/commands/` accessible to native agent frameworks, we use Router Skills.
- Identical `SKILL.md` routers are placed in `.agents/skills/job-search/`, `.opencode/skills/job-search/`, and `.claude/skills/job-search/`.
- When a user asks an agent to "run setup" or "apply for this job", the agent uses the router skill to map the request directly to the corresponding script in `.claude/commands/`.

## Why This Architecture is 10/10
1. **Zero Drift:** All logic shares the `.claude/commands/` and `.claude/skills/job-application-assistant/` folders. Modifying a workflow once updates it for all AI tools.
2. **Backward Compatibility:** Legacy Claude Code slash commands (`.claude/commands/`) were replaced with thin wrappers that redirect to `.claude/commands/`, ensuring old muscle memory still works.
3. **True Interoperability:** Whether you prefer OpenCode's rapid execution, Claude's deep reasoning, or Antigravity's autonomous workflows, the repository behaves identically.

## System Workflow Diagram
1. **User input** ➔ **AI Agent (OpenCode/Claude)**
2. **AI Agent** reads ➔ **Router Skill (`SKILL.md`)**
3. **Router Skill** triggers ➔ **Mode Script (`.claude/commands/apply.md`)**
4. **Mode Script** pulls data from ➔ **`AGENTS.md` & `.claude/skills/job-application-assistant/*.md`**
5. **AI Agent** executes logic ➔ **Outputs PDFs in `cv/` and `cover_letters/`**
