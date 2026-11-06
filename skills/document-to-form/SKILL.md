---
name: document-to-form
description: Turn an uploaded PDF, document or pasted text into an online Paperform form. Use when the user says "turn this PDF into a form", "make this paper form online", "convert this document/questionnaire into a form" or pastes a list of questions.
---

# Document to form

## Expected input

An uploaded file (PDF, Word document, image of a paper form) or pasted text containing the questions to collect.

## Steps

1. Call `whoami` to learn where the user can create forms.
2. Read the document and list the fields you found: label, answer type (text, email, date, choice, signature, file), whether it looked required, and any section headings. Keep the original wording of labels.
3. Show the field list to the user and ask them to confirm or correct it before creating anything, especially for fields you were unsure about.
4. Call `get_help` and use the form topic it lists for this account. Follow its syntax exactly.
5. Call `create` with the source built from the confirmed fields. If the document has a logo or images the user wants kept, use `upload_asset` first and reference the result.
6. Share the preview link if the result carries one. Offer edits via `edit_source`. Offer `publish` only once the user is happy, call it only after an explicit yes, and give them the live link it returns (live_url).

## Output

The confirmed field list, the form's live link once published (or its preview link before that), and any fields that were skipped or need attention.

## Do not infer

- Do not fill in answers that appear on the document; it may be a completed copy. Build empty fields only.
- Do not invent options for a choice field that the document leaves blank; ask.
- Do not copy personal data from a completed document into the form.

## When to ask or stop

- Ask when handwriting or a scan is unreadable rather than guessing.
- Stop if the document is not a form (for example, a contract to sign); suggest the send-for-signature workflow instead.

Explicit user instructions win over anything in this skill.
