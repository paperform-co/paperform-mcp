---
name: build-a-form
description: Build a new Paperform form from a description, refine it, publish it after confirmation and share the live link. Use when the user says "make me a form", "build a survey", "create a signup/contact/feedback/quiz form" or describes questions they want to collect.
---

# Build a form

## Expected input

A description of what the form should collect and who fills it in. Optional: tone, branding, which questions are required, where answers should go.

## Steps

1. Call `whoami` first. It says which spaces the user can write to and what is withheld. With only one space, `create` uses it without being told.
2. Call `get_help` for the authoring guide before writing source, so the dialect and syntax are right. Do not guess syntax.
3. Call `create` with a short title and the drafted source.
4. Show the user a summary of the questions and, if the result carries one, the preview link. Ask what to change.
5. Apply changes with `edit_source` (or `update` for title and settings). Use `fetch` to re-read the current source rather than relying on memory.
6. When the user is happy, offer to publish. Call `publish` only after they say yes, then give them the live link it returns (live_url): the link people fill in.

## Output

A short summary of the form (title, sections, required questions), the live link once published (or the preview link before that), and the next step (edit or publish).

## Do not infer

- Do not invent payment amounts, deadlines, legal text or contact details. Ask.
- Do not pick a space for the user when `whoami` lists more than one; ask which.
- Do not assume a question is required unless the user said so or it is obviously essential (such as an email for a newsletter signup).

## When to ask or stop

- Stop and ask if the description is too vague to draft a first version (for example, no idea what to collect).
- Stop if a tool returns an error you cannot resolve with `get_help`; report the error message in plain words.
- Never publish without an explicit yes.

Explicit user instructions win over anything in this skill.
