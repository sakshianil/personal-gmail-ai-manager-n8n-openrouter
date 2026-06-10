# GitHub Showcase Description

I built a reusable Gmail AI Manager using n8n, OpenRouter, Gmail, and Google Sheets.

The workflow reads new Gmail messages, extracts the full email body, asks an LLM to classify the email into structured categories, applies Gmail labels, creates draft replies for business leads, and logs every AI decision to Google Sheets.

The original version was personalized for my own workflow, but I converted it into a generic template so others can adapt it for their own inbox, startup, freelance work, research, job search, or client communication.

## What I learned

- How to design practical AI automation workflows with n8n
- How to run automation locally instead of relying only on cloud SaaS tools
- How to use OpenRouter as an LLM layer inside automation pipelines
- How to force structured JSON output from an AI model
- How to add safety checks before taking action on emails
- How to combine Gmail labels, draft replies, and Google Sheets logs into one workflow
- How to turn a personal automation into a reusable portfolio project
- How Claude Code plus MCP can help users modify workflow JSON more easily

## Why this matters

Many people are looking for cost-effective AI automation. This project shows that you can build a useful AI inbox assistant with local n8n, OpenRouter, Gmail, and Google Sheets without starting with an expensive SaaS stack.

The goal is not to replace human judgment. The goal is to reduce inbox noise, identify useful opportunities, create draft replies, and keep a decision log while the user remains in control.

## Suggested short post

I built a local-first Gmail AI Manager using n8n, OpenRouter, Gmail, and Google Sheets.

It classifies new emails, applies Gmail labels, drafts replies for business leads, and logs every AI decision in Google Sheets.

The first version was personalized for my own workflow, but I converted it into a reusable GitHub template so others can adapt it for their own inbox.

Best part: it is designed for n8n running on localhost, so it can be a cost-effective learning project before moving to any paid automation platform.
