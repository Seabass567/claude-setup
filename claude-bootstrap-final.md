# Claude Bootstrap Setup Prompt

> **How to use this:** Copy everything inside the box below and paste it into a fresh Claude chat (desktop app preferred). Claude will guide you through the full setup interactively — asking you a few questions and then doing the work for you.

---

```
Hi Claude. I'd like you to help me set up my environment so I can work with you as effectively as possible. Please work through the following steps with me one at a time, asking for any information you need before proceeding. Don't rush — check in with me at each stage before moving to the next.

---

## Step 1 — Check my setup

First, tell me:
- Are you running as the desktop app or the web app?
- If desktop: confirm you have access to my local file system.
- If web: let me know I'll need the desktop app for full setup and explain how to get it (claude.ai/download).

---

## Step 2 — Obsidian vault

Ask me where my Obsidian vault is located (or whether I have Obsidian installed at all).

- If I don't have it: tell me to download it from obsidian.md, then come back and continue.
- If I do: ask me for the full path to my vault folder (e.g. ~/Documents/Obsidian or ~/Vault).

Once I give you the path:
1. Save it to your memory: "User's Obsidian vault is at [path]. Save all project notes, research summaries, and session outputs here as .md files unless told otherwise."
2. Create a folder called ClaudeProjects/ inside the vault if it doesn't already exist.
3. Inside ClaudeProjects/, create a file called README.md with this content:

# Claude Projects

This folder contains notes, research, and session outputs from Claude.

## Structure
- Each project gets its own subfolder: ClaudeProjects/ProjectName/
- Each project folder should contain:
  - brief.md — what the project is, who it's for, current status
  - research.md — findings, competitors, references
  - log.md — decisions made, things tried, next steps

## How to use with Claude
At the start of a new chat, say:
"Read my project brief at ~/[your vault path]/ClaudeProjects/[ProjectName]/brief.md before we start."
Claude will pick up context instantly without needing a long conversation history.

---

## Step 3 — Skills folder

Ask me if I want to set up a local skills folder (explain briefly: skills are reusable instruction files that tell Claude how to behave for specific tasks — brand voice, research format, client profiles, etc.).

If yes:
1. Ask where I want the skills folder (suggest ~/Documents/ClaudeSkills/ as a default).
2. Create the folder with the following starter files:

**brand-voice.md**
```
# Brand voice skill

Use this skill when writing any copy, emails, or content on behalf of the user.

## Tone
- [User to fill in: e.g. "Friendly but professional. Direct. No corporate jargon."]

## Language rules
- [User to fill in: e.g. "Use contractions. Write in second person. Avoid passive voice."]

## Do not
- [User to fill in: e.g. "Don't use 'leverage', 'synergy', 'circle back', or exclamation marks."]

## Examples
- [User to fill in: paste 2-3 sentences that sound right]
```

**research-template.md**
```
# Research skill

Use this skill when conducting research on a topic, market, or competitor.

## Output format
1. Summary (3-5 sentences max)
2. Key players / competitors (name, what they do, pricing if known, notable strength/weakness)
3. Technology or approach used in this space
4. Where there's opportunity or differentiation
5. Sources (URLs where possible)

## Rules
- Flag anything you're uncertain about rather than stating it as fact
- Save output as research.md in the relevant ClaudeProjects subfolder
- Ask for more sources if you're unsure of the quality of what you're finding
```

**token-habits.md**
```
# Token management rules

Follow these rules in every session to keep context lean and costs low.

- Default model: Sonnet for most tasks. Haiku for summaries, email replies, low-effort tasks. Opus only for complex planning or strategy sessions.
- Start new chats for new topics — do not accumulate unrelated history in one thread.
- When starting a new chat on an existing project, read the project brief.md first rather than asking the user to re-explain.
- Do not paste entire documents unless asked. Summarise first, then ask if more detail is needed.
- Save outputs (research, plans, notes) to the Obsidian vault rather than keeping them only in chat.
```

3. Save a memory: "User's skills folder is at [path]. Reference relevant skill files at the start of tasks where they apply."

---

## Step 4 — Memory setup

Save the following to your memory (confirm with me before saving):

- My name: [ask me]
- My role / what I do: [ask me — one or two sentences]
- My primary working context: [ask me — e.g. "freelancer", "small team", "agency with clients", etc.]
- Default output format: save notes as .md to Obsidian vault, keep responses concise and direct
- Default model preference: Sonnet for most work, Haiku for lightweight tasks, Opus sparingly

---

## Step 5 — First project (optional)

Ask me if I'm currently working on a project I'd like to set up right now.

If yes:
1. Ask me for the project name.
2. Create a folder: ClaudeProjects/[ProjectName]/
3. Create brief.md and ask me to describe the project — what it is, who it's for, what stage it's at. Write up a clean brief from my answer and save it.
4. Ask if I want to do a quick research pass on anything related to the project now.

---

## Step 6 — Summary

Once all steps are done, give me a clean summary of what was set up:
- Vault location
- Skills folder location
- What's saved to memory
- Any projects created
- What to do at the start of my next Claude session (one-line instruction)

Then ask if there's anything I want to adjust before we finish.
```

---

## What this prompt does

When pasted into Claude, it will:

1. Check whether you're on the desktop app (required for full setup)
2. Find or help you install Obsidian and set up a vault
3. Create a structured `ClaudeProjects/` folder inside your vault with a template system
4. Set up a `ClaudeSkills/` folder with three starter skill files (brand voice, research template, token habits)
5. Save your name, role, and preferences to Claude's memory
6. Optionally create your first project brief
7. Give you a clean summary of everything that was set up

---

## Requirements

- **Claude desktop app** (web app won't have file system access)
- **Claude Pro plan** (for Opus access and higher limits)
- **Obsidian** installed — [obsidian.md](https://obsidian.md) (free)

---

## After setup

At the start of any new Claude session, say:

> *"Read my project brief at ~/[vault]/ClaudeProjects/[ProjectName]/brief.md and load my skills from ~/[skills folder] before we start."*

Claude will have full context without needing a long conversation history. New chat, zero wasted tokens.
