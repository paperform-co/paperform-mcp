---
name: client-onboarding
description: Set up a client onboarding flow across Paperform, Stepper and Papersign - an intake form, a workflow that records each new client in another app, and an agreement sent for signature. Use when the user says "set up client onboarding", "intake form and engagement letter", "when a client signs up, add them to my sheet and send the contract".
---

# Client onboarding

## Expected input

What to ask new clients, where client details should go (for example a Google Sheet or a CRM), and which agreement or engagement letter they sign.

## Steps

1. Call `whoami` to see which spaces the user can write to and whether Stepper and Papersign are available. If one isn't, say so and offer to build the parts that are.
2. Agree the plan with the user in plain words before building: the form's questions, what the workflow does with each submission, and which document is sent to whom.
3. Build the intake form as in the build-a-form skill: `get_help`, then `create`. Don't publish yet.
4. Find the agreement template with `search` or `list` and `fetch` it to see its signer roles and fields. If there's no template, stop and ask the user to provide one.
5. Build the workflow as in the build-a-workflow skill, triggered by the intake form: check accounts, `create`, then offer `test_action` on each step that writes to another app, asking before each because it runs the step for real. If the workflow can send the agreement through Papersign, add that as its last step, filled from the form's answers. If it can't, tell the user, and offer to send each agreement with `send_document` when they ask.
6. Show the user a summary of all three parts and how answers flow from the form into the workflow and the document.
7. Publish only after an explicit yes. Publish the workflow before the form, so no submission arrives before the workflow is live. Give the user the form's live link (live_url).

## Output

The form's live link, the workflow's trigger and steps, the template used and who signs, and anything left for the user to do.

## Do not infer

- Do not invent legal terms, fees, signer emails or client details.
- Do not send a real document to test the flow. `test_action` runs a step for real, so ask before each one.

## When to ask or stop

- Always stop before `publish`, `send_document`, `run_workflow` and each `test_action`, and get a clear yes.
- Stop if any part fails and explain which part, rather than leaving a half-built flow live.

Explicit user instructions win over anything in this skill.
