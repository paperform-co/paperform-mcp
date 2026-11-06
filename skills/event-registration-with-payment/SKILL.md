---
name: event-registration-with-payment
description: Build an event or workshop registration form that collects attendee details and takes payment, then publish it after confirmation. Use when the user says "registration form with payment", "sell tickets", "take bookings and payment for my event/class/workshop".
---

# Event registration with payment

## Expected input

The event name, date and place, ticket types and their prices and currency, attendee details to collect, and any capacity limit.

## Steps

1. Call `whoami` to see which spaces the user can write to. Taking real payments needs a connected payment provider; state that plainly if it applies.
2. Collect anything missing: ticket names, prices, currency, capacity, refund wording. Never guess a price.
3. Call `get_help` for the authoring guide, including the payment or products section, before drafting source.
4. Call `create` with the registration questions and the payment step or products.
5. If a payment app needs connecting, use `connect_app` and pass the link it returns to the user; do not attempt to connect it yourself.
6. Show the summary: questions, ticket types, prices, currency, capacity. Ask the user to confirm every amount.
7. Apply changes with `edit_source` or `update`.
8. Ask for explicit confirmation before calling `publish`, restating the prices that will go live, then give the user the live link it returns (live_url).

## Output

A summary of the registration form with each ticket type and price, and its live link once published (or the preview link before that).

## Do not infer

- Do not invent prices, currencies, taxes, dates or capacity.
- Do not state that payments are working until the payment app is connected.
- Do not mention plans or costs of Paperform itself. If a feature needs a different plan, say only that, and link the informational plans page only if a tool result provides one.

## When to ask or stop

- Always stop before `publish` and get a clear yes.
- Stop if a tool reports that payments are unavailable for this account, and tell the user why.

Explicit user instructions win over anything in this skill.
