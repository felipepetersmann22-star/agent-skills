---
name: usage-saving
description: Use before starting a task, pipeline, subagent plan or new scheduled job, or when asked to make an assistant setup cheaper without losing quality. Right-sizes the work, reads less, waits instead of polling, and routes to the focused skills for chats, routines, delegation and reuse.
license: MIT
---

# Usage saving

Goal: the same useful result with fewer model calls, less context read, and fewer wake-ups. Spend usage only where it changes the result.

This is the entry point of a small set. Use the focused skill when the task is mainly about one area:

| Area | Skill |
|---|---|
| Long chats, summaries, handover notes | `lean-chats` |
| Scheduled jobs, triggers, digests, watches | `frugal-routines` |
| Subagents, workers, effort levels, briefs | `cheap-delegation` |
| Checking skills, notes and files before researching | `reuse-before-research` |
| Tidying one assistant: handover, memory, files | `clean-and-compact` |
| Weekly review of the whole setup | `weekly-cleanup-review` |

If your platform has its own usage report or a built-in skill for checking plans, limits and billing, let it answer questions about real usage figures. This set covers how work is designed, not billing.

## 1. Right-size first
Name the task's shape before doing anything:
- **Lookup** (one fact): one search or one read, then answer. No plan, no workers.
- **Known steps**: do them in order, in one context.
- **Open-ended**: a short plan, then workers only where they pay (`cheap-delegation`).

Stop when the answer is good enough for the decision it feeds. Extra sources, drafts and review rounds that won't change the decision are waste.

## 2. Read less
- Read the smallest thing that answers: a search snippet before a page, a section before a document, the relevant lines before a whole file, a diff before a codebase.
- Don't reread what you already hold. In long tasks keep a short notes file and pass it on.
- Limit lists and searches (count, date range, filters) instead of paging through everything.

## 3. Batch and wait properly
- Put independent calls in one step. Put questions for a person in one message.
- Don't poll. Use a completion notice or event, or one wait sized to the expected run time.
- Before any wait, set a limit (about 1.5 to 2 times the expected time). When it passes, look once at status or the last lines of output. Still progressing: wait once more. Not progressing: stop it if safe and report what you saw. Never loop waits without a limit.
- Report once at the end, not a running commentary.

## 4. Reviewing an existing setup
For each chat, job or pipeline ask: how often does it run, and how often is its result used? What does each run read? Does it poll? How many workers does it start, and does each change the result? Does it message when nothing changed?

Then propose at most three changes, in this order: changes that remove whole runs or workers, then changes that cut what each run reads, then small trims. For each, say what is given up.

**Saying how much it saves**: name the quantity that drops, in the setup's own terms ("96 checks a day becomes 2"). Don't put a percentage or size on the usage saving; you can't see the bill. Offer to make the change and compare the usage report afterwards.

## Rules
- Never trade away correctness, safety checks, required reviews or approvals to save usage. Say what a step costs instead of cutting it.
- Don't delete notes, history or files to "read less". Archive and index them.
- Changes to schedules, plans, limits or someone else's setup wait for the owner's yes.
