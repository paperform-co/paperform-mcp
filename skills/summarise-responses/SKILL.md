---
name: summarise-responses
description: Find a form's submissions, filter them (for example by date) and summarise what respondents said, with counts taken only from the data. Use when the user says "summarise responses", "what did people say", "how many signups this week", "show me submissions to my form".
---

# Summarise responses

## Expected input

Which form (a name or link), and optionally a date range or other filter, and what kind of summary the user wants.

## Steps

1. Call `whoami` to confirm the user can read submissions.
2. Find the form with `search` (by name) or `list`. If several match, ask which one.
3. Call `list` for the form's submissions with the filters the user asked for (such as a date range). Page through results until you have all of them or a sensible cap; tell the user if you capped.
4. Use `fetch` for individual submissions when you need full answers.
5. For headline numbers, `get_analytics` can give views, starts and completion counts.
6. Write the summary: total responses in range, counts per choice for choice questions, recurring themes in free text with a few short representative quotes.

## Output

A concise summary with the counts you actually computed, the date range covered, and a note of anything excluded.

## Do not infer

- Never invent or estimate numbers. Every count must come from the returned data; if you could not load everything, say so.
- Do not reveal personal details (emails, phone numbers, addresses) unless the user asked for them.
- Do not guess the meaning of an ambiguous answer; quote it.

## When to ask or stop

- If a tool says the user lacks permission, stop and say so; do not try other routes around it.
- Ask before exporting or quoting large amounts of raw response data.

Explicit user instructions win over anything in this skill.
