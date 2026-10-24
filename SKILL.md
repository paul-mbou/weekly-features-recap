---
name: weekly-features-recap
description: >-
  Produces human-friendly weekly project recaps for PMs and non-developers from
  git history and Cursor transcripts. Outputs Recap, Standup, and Changelog in
  plain language. Use when the user asks for weekly recap, sprint summary, what
  we shipped, standup, changelog, bilan hebdomadaire, or résumé de la semaine.
---

# Weekly Features Recap (PM-friendly)

Turn raw project activity into a **clear, warm, non-technical** weekly report.
Default audience: **project manager, stakeholder, or non-dev teammate**.

## Mandatory workflow

Copy and track:

```
Recap progress:
- [ ] Step 1 — Collect raw facts (git + optional transcripts)
- [ ] Step 2 — Extract user-visible changes (subagent if large)
- [ ] Step 3 — Humanize (always — see humanize-guide.md)
- [ ] Step 4 — Deliver 3 sections: Recap → Standup → Changelog
- [ ] Step 5 — Self-check with quality checklist
```

### Step 1 — Collect raw facts

Run in parallel when possible:

```bash
git log --since="7 days ago" --pretty=format:"%h|%ad|%s" --date=short
git log --since="7 days ago" --stat --oneline
git diff --stat HEAD   # if many uncommitted changes
git status --short
```

Also scan Cursor agent transcripts from the last 7 days when available
(`agent-transcripts/*.jsonl`) for tasks the user explicitly requested.

**Keep internally:** commits, file areas, user requests.  
**Do not paste** file paths, class names, or stack traces into the final report.

### Step 2 — Extract user-visible changes

Translate technical work into **what users or the business will notice**.

| Raw signal | PM-friendly meaning |
|------------|---------------------|
| `event_list_screen`, tabs | Users can browse events by upcoming / saved / owned / past |
| `notification_service`, i18n | Task reminders now speak the user's language |
| `vendor_profile`, bottom bar | Visitors see a "Book vendor" button on profiles |
| `@Preview`, widgets | Faster design review for the team (internal) |
| splash, ic_launcher, assets | New app logo and launch screen |
| refactor, no UX change | *(Omit from Recap — internal only)* |

**Launch an explore subagent** when ANY of:
- More than 80 changed files
- More than 15 commits in the week
- Transcript + diff together exceed what you can skim in one pass

Subagent prompt (adapt paths):

```
Read git log and diff from the last 7 days for [PROJECT].
List ONLY changes a user, PM, or stakeholder would care about.
Group by product area (Events, Vendors, Notifications, Design, etc.).
No file paths, no class names, no jargon.
Max 15 bullets. French if the user writes in French.
Return: bullet list + "Not shipped yet" items + "Internal only" one-liner count.
```

Use the subagent output as input to Step 3 — not the final text.

### Step 3 — Humanize (always)

Read [humanize-guide.md](humanize-guide.md) and apply **every rule** before writing.

Read [examples.md](examples.md) for before/after tone.

Use [templates.md](templates.md) for structure.

**Language:** match the user's language (French by default if they write in French).

### Step 4 — Deliver three sections

Always produce **all three**, in this order:

1. **Récap / Recap** — 2-minute read for a PM  
2. **Standup** — Fait / En cours / Blocages / Priorités  
3. **Changelog** — Added / Changed / Fixed (user-facing only)

See [templates.md](templates.md).

### Step 5 — Quality checklist

Before sending, verify:

- [ ] No file paths, no `_Widget`, no `Provider`, no PR numbers unless asked
- [ ] Each bullet answers "So what?" for someone who doesn't code
- [ ] Recap ≤ 12 bullets; Standup ≤ 6 lines per section
- [ ] Jargon replaced (see humanize-guide.md glossary)
- [ ] Honest about uncommitted / not-yet-live work
- [ ] Pleasant to read — short sentences, active voice, no wall of text

## What to include vs omit

**Include**
- New screens, flows, buttons, notifications users will see
- Bug fixes users felt (wrong language, bookmark not updating, etc.)
- Branding / app store visible changes
- Translations and accessibility improvements
- Blockers affecting delivery dates

**Omit or one line under "Travail interne"**
- Refactors with no visible change
- Dependency bumps, lint, codegen (`.g.dart`)
- Cursor rules, skills, CI-only changes
- File renames, widget extraction

## Integration note

This skill **replaces** technical dump recaps. If `weekly-features-recap` was invoked,
never skip Step 3 even when git output is empty — use transcripts and state what was
discussed or planned.

## Additional resources

- Tone, glossary, anti-patterns: [humanize-guide.md](humanize-guide.md)
- Before/after examples: [examples.md](examples.md)
- Output templates: [templates.md](templates.md)
