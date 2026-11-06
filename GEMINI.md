# Paperform

The `paperform` MCP server works in the user's Paperform account: forms (Paperform), workflows (Stepper) and e-signatures (Papersign).

- Call `whoami` first. It says which spaces and products this connection can use.
- Before you create or edit a form or workflow, read the reference `get_help` points you to (its description lists the topics this account has). Follow what it returns.
- Check with the user before anything that publishes, sends, spends credits or can't be undone. The tools say when a confirmation is needed.
- Share the live link when a form is published, and report real counts when summarising responses.
- If a call says the connection needs to be reconnected, ask the user to run `/mcp auth paperform`.

The skills in `skills/` describe common jobs step by step.
