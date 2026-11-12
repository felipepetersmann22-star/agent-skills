---
name: clean-and-compact
description: Use when one assistant's chat, memory or files have built up, or when the user says clean up, refresh, compact, or start fresh. Waits for in-flight work, compacts what matters into a handover note, refreshes memory, archives old files instead of deleting them, and suggests usage cuts without changing anything on its own.
license: MIT
---

# Clean and compact

Goal: leave one assistant lean and fresh while keeping everything important. Never delete anything without the owner's explicit yes. Archive instead.

For a sweep across many assistants on a schedule, use `weekly-cleanup-review`, which runs this skill once per assistant.

## 0. Check timing
- If a project or task is mid-flight (open worker or subagent, waiting on a reply or approval, a build or deploy running), stop here. Tell the owner it will be cleaned once that work wraps, and do nothing else.
- Be frugal. Read recent chat and existing memory first. Don't re-read whole transcripts.

## 1. Compact the context into a handover
Write a short handover note, under one page, using the `lean-chats` template. It covers:
- What this assistant is for, and the owner's standing rules and preferences for it.
- Decisions made, each with a one-line reason.
- Open items and next steps, with owner and date.
- Key files, links, repositories and pages, as paths or URLs.
- Anything a fresh chat would otherwise have to ask again.

Save it as a dated file in the assistant's archive folder, for example `archive/<assistant>/handover-YYYY-MM-DD.md`.

## 2. Refresh memory
- Move lasting facts from the handover into memory: standing rules as profile facts, decisions as dated entries. Use shared memory only for facts every assistant needs.
- Remove memory facts that are outdated or contradicted, and write the corrected version.
- Never put addresses, emails, phone numbers, passwords, keys or card details in memory. Use the platform's secure vault if it has one.

## 3. Clean files
- List this assistant's working files: scratch folders, old drafts, duplicate exports, stale screenshots.
- Move superseded or duplicate files into `archive/<assistant>/YYYY-MM-DD/`. Don't delete them. Keep the latest version of each deliverable where it is.
- Compress big archive folders (for example `tar -czf`).
- Never touch files that belong to another assistant, a shared site or a shared repository.
- List anything that truly looks deletable and ask the owner before deleting it.

## 4. Cut ongoing usage
- Review this assistant's scheduled jobs with `frugal-routines`: less often, weekdays and waking hours, event triggers instead of polling, merge duplicates. Suggest only. Change nothing without the owner's yes.
- Flag repeated research or steps that should become a skill (`reuse-before-research`).

## 5. Report
Two or three sentences to the owner: where the handover is saved, what was archived, any deletions waiting for a yes, and up to three usage suggestions. If the chat is long and the work has wrapped, say it is safe to start this assistant fresh, because the handover and memory carry everything over.
