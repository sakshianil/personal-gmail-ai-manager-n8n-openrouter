# Customization Guide

This workflow is intentionally generic. Replace the default context with your own personal, freelance, startup, academic, creator, or company workflow.

## 1. Run it locally first

This project is designed for **n8n localhost**, not n8n Cloud.

Recommended beginner setup:

```bash
npm install n8n -g
n8n start
```

Then open:

```text
http://localhost:5678
```

Running locally is useful because:

- You can learn n8n without paying for cloud automation.
- You can test workflows safely before production use.
- You can keep the workflow under your own control.
- You can export/import JSON and version it on GitHub.

## 2. Customize the AI role

In the `OpenRouter - Classify Email` node, edit the system message.

Example:

```text
You are an intelligent Gmail triage assistant for a freelance designer. Classify client leads, invoices, project updates, newsletters, and spam.
```

For a job seeker:

```text
You are an intelligent Gmail triage assistant for a job seeker. Classify recruiter replies, interviews, rejections, applications, invoices, newsletters, and spam.
```

For a founder:

```text
You are an intelligent Gmail triage assistant for a startup founder. Classify investor emails, customer leads, supplier messages, invoices, legal emails, newsletters, and spam.
```

## 3. Customize categories

Default categories:

```text
IMPORTANT
BUSINESS_LEAD
NEEDS_REVIEW
DELETE_CANDIDATE
```

Possible alternatives:

```text
CLIENT_LEAD
INVOICE
URGENT_REPLY
NEWSLETTER
COURSE_UPDATE
FAMILY
SPAM_REVIEW
```

After changing categories, update:

- The OpenRouter prompt
- The Switch node routes
- Gmail label nodes
- Google Sheets column logic

## 4. Customize safety keywords

The workflow includes a safety override that prevents risky emails from being classified as delete candidates.

Examples of safety keywords:

```text
invoice, payment, contract, offer, supplier, customer, order, visa, job, university, tax, bank, legal, medical, government
```

Add keywords that matter for your own life or business.

## 5. Customize the draft reply style

For business lead emails, the AI can create a draft reply.

You can change the tone to:

- Formal
- Friendly
- Short and direct
- Founder-style
- Client-service style
- German-English bilingual
- Industry-specific

Recommended rule:

```text
Create draft replies only. Never send replies automatically.
```

## 6. Use OpenRouter cost-effectively

Start with a free or low-cost model through OpenRouter. Only upgrade to stronger models if needed.

Recommended testing approach:

1. Test on 20–30 real emails.
2. Check classification quality.
3. Improve the prompt.
4. Adjust safety keywords.
5. Change the model only if prompt improvements are not enough.

## 7. Optional Claude Code + n8n MCP workflow

Users who work with Claude Code can connect an n8n MCP server so Claude can help inspect or modify workflow JSON.

General pattern:

```json
{
  "mcpServers": {
    "n8n-local": {
      "command": "npx",
      "args": ["-y", "n8n-mcp"],
      "env": {
        "N8N_API_URL": "http://localhost:5678/api/v1",
        "N8N_API_KEY": "YOUR_LOCAL_N8N_API_KEY"
      }
    }
  }
}
```

Use this carefully. MCP gives an AI assistant tool access. Start with read-only or test workflows whenever possible.

## 8. Keep secrets out of GitHub

Never commit:

- API keys
- OAuth credentials
- real Gmail credential IDs
- private Google Sheet URLs
- private business prompts
- personal email content

The included `.gitignore` helps, but you must still review files before pushing.
