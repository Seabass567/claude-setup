# Basti's Claude Guide

A practical guide for getting the most out of Claude — whether you've never used it before or you're ready to go deeper with the desktop app, connectors, and power features.

---

## Table of Contents

1. [Setup](#1-setup)
2. [Web App vs Desktop App](#2-web-app-vs-desktop-app)
3. [Choosing a Model](#3-choosing-a-model)
4. [Chat and Planning](#4-chat-and-planning)
5. [Research Workflow](#5-research-workflow)
6. [File and Project Setup](#6-file-and-project-setup)
7. [Token Management](#7-token-management)
8. [Skills and Repositories](#8-skills-and-repositories)
9. [MCPs and Connectors](#9-mcps-and-connectors)
10. [Claude Code](#10-claude-code)
11. [Tips and Habits](#11-tips-and-habits)

---

## 1. Setup

### Step 1 — Create an account

Go to [claude.ai](https://claude.ai) and sign up. The free plan gives you access to Sonnet. A **Pro plan** unlocks Opus, higher limits, and the desktop app.

### Step 2 — Download the desktop app (recommended)

Available for Mac and Windows at `claude.ai/download`. The desktop app unlocks local file access, connectors, and co-work — capabilities the web app doesn't have.

### Step 3 — Set up a notes system

**[Obsidian](https://obsidian.md)** (free) is the recommended local markdown vault. Ask Claude to save project notes as `.md` files in your vault. This keeps your work AI-platform agnostic — readable anywhere, not locked to Claude or any other tool.

> **Memory tip.** Once Obsidian is set up, tell Claude: *"Save a memory that my Obsidian vault is at ~/Documents/Vault — use this for any project notes."* Claude will reference this location in every future session.

### Step 4 — Optional: voice input

**[TypeWhisper](https://typewhisper.app)** runs locally and converts speech to text you paste into Claude. Useful for longer, more detailed prompts without typing.

---

## 2. Web App vs Desktop App

Both work. But they're not equal.

### Web app

**Good for:** Quick questions, one-off tasks, using Claude on your phone or a shared machine, sharing conversation links.

**Limitations:** No local file access, no MCP connectors, no co-work support, can't read your local folders or projects.

### Desktop app ★

**Good for:** Any ongoing project work, file creation and organisation, connecting to external tools (Gmail, Drive, Notion, HubSpot, etc.), anything you want Claude to remember across sessions.

**The short version:** Use the web app to start. Switch to the desktop app as soon as you're doing real project work.

---

## 3. Choosing a Model

Three models. Getting this right affects both quality and cost.

| Model | Best for | Speed | Cost |
|-------|----------|-------|------|
| **Claude Opus** | Complex planning, strategy, architecture, high-stakes decisions | Slower | Highest |
| **Claude Sonnet** ★ | Research, writing, coding, most everyday tasks | Fast | Balanced |
| **Claude Haiku** | Email replies, quick summaries, low-effort tasks | Fastest | Lowest |

> ⚠️ **Use Opus sparingly.** It's expensive and slow. The vast majority of tasks that feel like they need Opus actually don't. Sonnet handles most work extremely well. Reserve Opus for genuine planning and strategy sessions only.

### Quick cheat sheet

| Task | Model |
|------|-------|
| Planning a new project | Opus — but only for the strategy session |
| Researching competitors | Sonnet |
| Writing copy or docs | Sonnet |
| Replying to emails | Haiku |
| Summarising a document | Haiku |
| Code review | Sonnet (Opus only if genuinely complex) |
| Everyday chat | Sonnet |

---

## 4. Chat and Planning

### Use chat for planning

Before you build anything — plan it. Describe what you're working on and ask Claude to help you:

- **Map out the problem** — what you're building, what assumptions you're making, what you might be missing
- **Identify the market** — competitors, differentiation, technology typically used
- **Break into phases** — clear deliverables and dependencies
- **Stress-test the plan** — *"What are the three most likely reasons this fails?"*

**Example planning prompt:**
> *"I want to build an app for guitar tuners. Research the existing tools in this space, identify how they work, find the top competitors, and help me understand where I could differentiate. Then help me plan Phase 1."*

### Projects — persistent context

Claude's built-in **Projects** feature groups related conversations and gives Claude persistent context — your role, your company, background on the work. Set this up for any ongoing engagement so you're not re-explaining everything every session.

---

## 5. Research Workflow

**Research → Plan → Build → Iterate**

Even if you think you know enough — do a short research pass. You'll find inspiration, surface blind spots, and give Claude the context it needs for better output later.

### Research tips

1. **Give Claude a clear scope.** Don't say "research X." Say: *"Research the top 5 competitors in [space], what technology they use, their pricing model, and where they're weak."*

2. **Feed it sources yourself.** Claude doesn't always find the best sources. If you've spotted a useful article or competitor site, paste the URL in and ask Claude to reference it. It's better at analysis than discovery.

3. **Ask for reusable output.** Request that research be saved as a `.md` file in your notes folder — searchable later and referenceable in future chats without wasting tokens.

4. **Enable web search.** Toggle it on in Claude.ai for research tasks. Claude's training data has a cutoff — web search gives it access to live sources.

> **Watch out for:** Claude hallucinating competitor details, pricing, or sources. Always verify specific claims against the actual site before acting on them.

---

## 6. File and Project Setup

One of the desktop app's biggest advantages — Claude can create and organise files on your machine.

**Example prompt:**
> *"I'm starting a freelance design studio. Create a local file structure for managing client projects, proposals, assets, and invoices. Save it to ~/Documents/Studio."*

Works well for new businesses, client work, side projects, expense trackers, and spreadsheets. Tell Claude what you're building and it'll generate a sensible structure rather than you doing it manually.

> Markdown files in Obsidian work with any tool — your notes and context stay with you even if you switch platforms.

---

## 7. Token Management

**This is the section most people skip — and it's the one that costs them the most.**

### How tokens actually work

Every message uses tokens (roughly one word = one token). What most people don't realise: **every prompt includes your entire conversation history.** Message 1 is just your prompt. By message 6, you're also resending five full exchanges worth of history — every single time. After 4–5 replies in a single chat, you're burning a significant portion of each message just on dead context.

Long threads don't make Claude smarter. They make it slower and more expensive.

### How to fix it

**Start new chats often.** A new chat doesn't mean starting from scratch — it means not carrying dead weight.

**Use your MD files as context.** Keep a well-maintained markdown file per project. At the start of a new chat, point Claude at it:
> *"Read my project brief at ~/Vault/ProjectX.md before we start."*

Claude gets full context instantly — no long history needed. This is how you start fresh without starting over.

**Keep documents lean.** Only paste in what's needed. Don't dump entire codebases or long documents into the chat — summarise first and let Claude ask for more if needed.

**Use skills instead of repeating yourself.** If you're explaining your brand voice or project requirements in every chat — that's wasted tokens. Write it once as a skill file and reference it.

**Pick the right model.** Haiku costs a fraction of Opus. If the task is summarising an email — use Haiku. Burning Opus tokens on low-stakes work is the fastest way to hit your limits.

**For developers — use RTK (Rust Token Killer).** RTK is specifically built to significantly reduce tokens used in Claude Code sessions. If you're running Claude Code regularly, it's a meaningful saving.
→ [github.com/drbh/rtk](https://github.com/drbh/rtk)

---

## 8. Skills and Repositories

### What are skills?

A skill is a markdown file with detailed instructions for a specific use case. Write it once, reference it in any conversation. Claude follows it without you re-explaining.

**Example skill (`google-ads.md`):**
```
When writing Google Ads headlines:
- Use sentence case always
- Max 30 characters per headline
- Lead with the benefit, not the feature
- Avoid exclamation marks
- Reference examples/ folder for approved copy
```

### Skills to create first

| Skill | What to include |
|-------|----------------|
| Brand voice | Tone, language rules, what to avoid, example sentences |
| Research template | Output format, sources to check, sections to always cover |
| Code style | Languages, formatting rules, naming conventions |
| Client profile | Who they are, what they care about, language preferences |
| Ad copy rules | Character limits, CTA patterns, what's worked before |
| Meeting notes | Format, sections, follow-up structure |

### Public repositories

Don't build from scratch — the community has already done a lot of the work:

- **Awesome MCP Servers** — curated list of MCP servers for databases, APIs, and local tools
  → [github.com/punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers)

- **Anthropic MCP GitHub** — official specs, reference implementations, and first-party servers
  → [github.com/modelcontextprotocol](https://github.com/modelcontextprotocol)

- **Claude Connectors Directory** — browse and install official connectors directly from within Claude
  → [claude.ai/settings/connectors](https://claude.ai/settings/connectors)

---

## 9. MCPs and Connectors

MCPs (Model Context Protocol) let Claude connect directly to your tools. Instead of copy-pasting between apps, Claude reads from and writes to them directly.

### Installing connectors

1. Open the desktop app → Settings → Connectors
2. Connect your most-used tools first (Gmail and Drive are useful for almost everyone)
3. Reference them naturally in conversation: *"Check my Gmail for anything urgent this week and give me a summary."*

### Most useful connectors

**Gmail**
Claude can read your inbox, summarise what's been happening, draft replies, flag important threads, and write outgoing emails. Particularly useful for high-volume inboxes — ask for a morning briefing and it'll surface what actually needs your attention.

**Google Drive**
Claude can see all your Drive files — read docs, summarise reports, reference old proposals, and create new files directly. Especially useful when starting a new client project and you want Claude to read existing work for context.

**Google Calendar**
Check upcoming meetings, draft prep notes, suggest scheduling blocks, plan your week around existing commitments.

**Notion / Linear**
Read and create tasks, update project docs, pull context from your workspace — Claude becomes a genuine project management assistant.

**HubSpot**
Connect Claude to your CRM and ask it to read contact histories, analyse pipeline health, identify follow-up gaps, and diagnose why deals are stalling. Useful for sales teams who want analysis without logging into HubSpot and running manual reports.

**GitHub**
Review PRs, search issues, read repo contents — without leaving Claude. Pairs well with Claude Code.

> **Advanced:** You can run local MCP servers to connect Claude to tools without official connectors. See the repositories listed in the Skills section for community-built options covering dozens of additional services.

---

## 10. Claude Code

Claude Code is a command-line tool that gives Claude direct access to your codebase. It reads files, writes code, runs commands, and iterates — all from your terminal.

Rather than copying code back and forth from a chat window, Claude Code works directly inside your project.

### Getting started

1. **Install:** `npm install -g @anthropic-ai/claude-code` (requires Node.js)
2. **Navigate to your project** and run `claude` — it reads your project structure automatically
3. **Give it a task:** *"Add input validation to the login form"* or *"Why is this function returning undefined?"*

**Good use cases:** building features, refactoring, writing tests, migrating frameworks, debugging, spinning up new projects.

> **Token note:** Claude Code can burn through tokens quickly. Use RTK (Rust Token Killer) to significantly reduce usage — see [Section 7](#7-token-management). Keep git commits small so you can revert if something goes wrong.

---

## 11. Tips and Habits

**Always research before building.** Even if you think you know enough. It surfaces blind spots and gives Claude better context for everything that follows.

**Give Claude references, not just instructions.** Show it examples of sites with a style you like. Paste in copy with the right tone. Claude works better with models to reference than with abstract descriptions.

**Push back when something's not right.** Claude isn't always correct on the first try. Be specific: *"The tone is too formal — rewrite this like you're talking to a friend."*

**Build skills for recurring work.** Anything you explain more than twice should be a skill file. Client profiles, writing guidelines, code conventions — write it once.

**Keep conversations scoped.** One conversation per topic. Mixing unrelated projects in one thread wastes tokens on irrelevant history and dilutes Claude's focus.

**Treat Sonnet as your default.** Reach for Opus when you genuinely need depth on a complex decision. For everything else — Sonnet is more than capable and significantly cheaper.

**Maintain your markdown files.** An up-to-date project `.md` file means any new chat can get full context instantly. This is how you start fresh without starting over.

**Use memory intentionally.** Tell Claude things you want it to remember across sessions: your role, your vault location, your output preferences. Saves tokens and time.

---

*Guide covers Claude as of 2025. For the latest on pricing, model availability, and features:*
*[claude.ai](https://claude.ai) | [docs.claude.com](https://docs.claude.com) | [support.claude.com](https://support.claude.com)*
