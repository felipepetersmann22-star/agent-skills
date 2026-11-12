---
name: weekly-cleanup-review
description: Use for a scheduled weekly (or on-demand) review of a whole multi-assistant setup. Backs up skills and workflows, runs clean-and-compact on every assistant that is idle, skips anything mid-project, flags duplicate skills and routines, and proposes at most three usage cuts in one short report for the owner to approve.
license: MIT
---

# Weekly cleanup review

The workflow that ties the pack together. One run a week keeps every assistant lean without anyone having to remember. It archives, writes notes and proposes. It never deletes anything or edits a schedule without the owner's yes.

## Schedule
- One routine for the whole setup, not one per assistant.
- A weekday morning inside the owner's waking hours, with a flexible start window (`frugal-routines`).
- Start from last week's report and look only at what changed since.

## 1. Back up skills and workflows
Copy the current skills and workflow or routine definitions into a dated archive folder (for example `archive/skills-workflows/YYYY-MM-DD/`) before proposing any change to them.

## 2. Check usage
If the platform has a usage report, read which assistants and routines used the most this week. Use it to decide where to look first. Don't estimate savings yourself.

## 3. Sweep the assistants
For each assistant, most-used first:
- **Mid-project?** (running worker, build or deploy, waiting on a reply or approval, touched by the owner in the last day or two). Skip it and list it as "in progress, next run".
- **Long and idle?** Run `clean-and-compact` on it: handover note, memory refresh, file archive.
- **Short and tidy?** Leave it alone. Don't read it in full.

## 4. Find duplicates
- Skills that cover the same task: propose merging into the better one (`reuse-before-research`). Don't delete the other; archive it.
- Routines that read the same sources or serve the same reader at similar times: propose merging into one run (`frugal-routines`).

## 5. Propose cuts
Run the setup review in `usage-saving` (section 4). At most three changes, biggest first: remove or merge runs and workers, then cut what each run reads, then small trims. State each in the setup's own terms and say what it gives up.

## 6. Report
Fill in `assets/cleanup-report.md` and send it as one short message. If nothing changed since last week, send one line, or nothing if the owner prefers. Save the report in the archive folder so next week's run can start from it.

## Never
- Interrupt live work to tidy it.
- Delete files, notes, skills or chat history without an explicit yes.
- Change schedules, plans or another person's setup without their yes.
- Skip reviews, approvals or safety checks to save usage.
