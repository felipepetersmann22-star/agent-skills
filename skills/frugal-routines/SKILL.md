---
name: frugal-routines
description: Use when creating, reviewing or merging scheduled jobs, digests, monitors, reminders or watches, or when asked to make them cheaper. Defaults to weekday waking hours and flexible start times, prefers event triggers to polling, merges overlapping jobs, and stays quiet when nothing changed.
license: MIT
---

# Frugal routines

A scheduled job costs usage every time it wakes, whether or not it finds anything. Design it around when someone will act on the result, not around how often the source changes. If your platform has its own guidance for creating routines, follow it for the mechanics; this skill adds the cost checks.

## Before adding a job
1. **Does it need to exist?** Could it be one more step in a job that already runs?
2. **Is there an event for it?** If the thing you're waiting for (a new email, a pull request, a mention, a form submission) can trigger the job directly, use the trigger. Timers that check "anything new?" are polling.
3. **When will the result be used?** Schedule just before that.

## Defaults
- **Weekdays and waking hours.** Pin both the days and the hours. Leaving either open quietly adds nights or weekends. Use the owner's real hours when known.
- **Go outside that window only for a stated reason**: the owner asked for it, the subject is time-critical (an incident, or a cut-off that falls outside working hours), the event only happens then, or the job is about personal life (health, pets, habits) where every day matters.
- **Coarsest cadence that still lets someone act in time.** Start slow; tighten only when the delay had a real cost.
- **Flexible start windows.** Let the job start within a window around the hour instead of on the exact minute, unless the minute matters (a meeting start, a one-off reminder). If it must be ready by a time, start early enough and don't allow late starts.
- **Read only what's new since the last run**: a date, an ID or a cursor, not the whole inbox or feed each time.

## Stay quiet
- If nothing changed, send nothing. No "no change" messages.
- Alert at once only on what the owner would act on (a price under target, a refund request, an outage). Everything else waits for a digest.
- Give watches an end: a date, a target, or a number of runs. A watch with no end runs forever.

## Merging duplicates
When two jobs read the same sources or serve the same reader at similar times, merge them into one run with sections. Keep them separate only if they go to different people or need different timing for a reason you can state.

## Reviewing existing jobs
List each job with: trigger or schedule, days and hours, what it reads, who reads the result and when, what it sends when nothing changed. Then propose changes in this order: remove or merge jobs, switch timers to triggers, narrow days and hours, cut what each run reads, stop empty messages.

State the change in the job's own terms ("every 15 minutes, all week" becomes "twice a day on weekdays, message only below target"). Don't estimate the usage saving as a number.

Never edit someone's existing jobs without their yes. Propose, then change what they approve.
