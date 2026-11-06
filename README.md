# Paperform for Gemini CLI

Create forms that do more, from Gemini CLI. Take payments and bookings, get documents signed, automate what happens next and analyse the responses. This extension connects Gemini CLI to your Paperform account and adds skills that show it how to do each job well.

## Install

```
gemini extensions install https://github.com/paperform-co/paperform-gemini-extension
```

Then start Gemini CLI and run `/mcp auth paperform`. Sign in with your Paperform account (or create one) and choose what Gemini CLI may do. It works on every Paperform plan, including Free.

## What you can ask for

- **Forms.** Describe what you need and Gemini CLI builds it in your account: an order form that takes payment, a booking form for 30-minute calls, a quote form that calculates the total. Add coupons, conditional logic and your colours and fonts. Connect your Stripe, Square, PayPal or Braintree account in Paperform and Gemini CLI does the rest. You can also turn a PDF or a list of questions into a form. Publish it when you're happy, then ask for a summary of the responses.
- **Workflows.** Ask Gemini CLI to act on each new submission or other trigger: add a row to Google Sheets, send an email, update your CRM. It builds the workflow, tests each step against your connected apps, and explains what happened when a run fails.
- **E-signatures.** Pick a template, say who signs and what to fill in, and it sends the document for signature once you confirm. Ask who still needs to sign, or cancel a document that went out by mistake.

Try:

- "Make an order form that takes payment and adds each order to my Google Sheet."
- "Make a booking form for 30-minute calls, weekdays 9 to 5."
- "Make a client intake form and send each new client our engagement letter to sign."

## Skills

| Skill | Use it to |
| --- | --- |
| `build-a-form` | Build a form from a description and publish it |
| `document-to-form` | Turn a PDF, document or pasted questions into a form |
| `event-registration-with-payment` | Build a registration form that takes payment |
| `build-a-workflow` | Build, test and publish a workflow |
| `send-for-signature` | Prepare a document from a template and send it for signature |
| `summarise-responses` | Summarise a form's responses with real counts |
| `client-onboarding` | Set up an intake form, a workflow and a signed agreement together |

## How it works

The extension contains skills (Markdown instructions), a context file and one remote MCP server, `https://api.paperform.app/mcp`. It runs no code on your computer.

When you connect, you sign in through Paperform's own sign-in page and choose what Gemini CLI may do. It then works only in the account and spaces you approved. Requests go from Gemini CLI to Paperform's server over HTTPS; the extension sends data nowhere else. It checks with you before it publishes, sends or deletes anything.

Workflows run on Stepper and e-signatures on Papersign, both part of Paperform. Already use Stepper or Papersign on their own? Sign in with that account, and you get the tools for the products it has.

## Links

- About the connector: https://paperform.com/mcp/
- Help: https://paperform.com/help/
- Privacy policy: https://paperform.com/privacy/
- Terms: https://paperform.com/terms/

## Licence

MIT. See [LICENSE](LICENSE).
