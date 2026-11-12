---
name: cheap-delegation
description: Use before spawning subagents or workers, choosing a reasoning effort level, or writing a brief for another agent, and when following up on delegated work. Starts at normal effort and raises it only on retry, reuses one worker per workstream, caps fan-out, and keeps briefs tight so nothing is researched twice.
license: MIT
---

# Cheap delegation

Each worker starts with an empty head and has to be told or rediscover everything. Several workers in parallel usually cost several times one agent doing the work. Delegate when it pays: the pieces are independent, too big for one context, or need a genuinely separate view (a blind reviewer, independent advisors).

## Should this be delegated?
- One lookup or a few known steps: do it yourself.
- Independent pieces that each need real work: delegate, one worker per piece.
- A required independent check (blind review, separate reviewers): keep it. That independence is the point; don't merge it away to save usage.

Cap the count before starting. If you drop planned workers, say in one line when they'd be worth adding back.

## Effort: low first, high on retry
- Start at normal or low reasoning effort for lookups, formatting, extraction and well-specified tasks.
- Raise the effort only when a result comes back wrong, thin or contradictory, and say why in the retry brief.
- Use high effort from the start only for work where a mistake is expensive and hard to spot (security, legal, money, irreversible changes).

## Tight briefs
Use `assets/worker-brief.md`. A brief gives:
- the goal in one or two lines and the decision it feeds;
- only the inputs needed (facts, files, links), not the whole conversation;
- what's already known, so it isn't researched again;
- the output format and a length cap;
- when to stop, and what to do if blocked.

## One worker per workstream
- Keep a worker that already holds a workstream's context and send its follow-ups back to it.
- If it's gone, start the new worker with the earlier worker's saved findings, not from scratch.
- Ask workers to return results in a form you can save (a short table or notes file), so follow-ups can reuse them.

## Merging results
Compare and merge in the main agent when the results are short and structured. A separate merge worker is only worth it when the combined results don't fit or need a specialist.

## Quality floor
Cheaper delegation still needs the same sources, dates and checks. Tell workers to cite primary sources and date anything that changes (prices, rules, versions).
