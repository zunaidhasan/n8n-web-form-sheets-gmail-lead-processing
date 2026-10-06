# n8n Web Form → Sheets + Gmail Lead Processing

Complete n8n workflow that turns website contact form submissions into structured, AI-classified leads.

## What it does

1. Receives new leads via **Webhook** from your website form
2. Cleans and structures the data
3. Checks for **duplicate emails** in Google Sheets
4. Uses **OpenAI** to:
   - Classify the service requested
   - Extract approximate budget
   - Assign Lead Priority (`HOT` / `WARM` / `COLD`)
   - Generate a short AI summary
5. Saves the lead into **Google Sheets** (Priority & Service as separate columns)
6. Sends a **Gmail notification** to the agency owner with priority in the subject line  
   Example: `New HOT Lead – Website Inquiry`

## Features

- Website form webhook trigger
- Data cleaning & normalization
- Basic duplicate-lead detection
- OpenAI classification + extraction + summary
- Google Sheets storage
- Gmail alert with priority in subject
- Basic error handling / safe fallbacks
- Sticky notes inside the workflow for easy setup

## Files

| File | Description |
|------|-------------|
| `workflow/AI_Lead_Processing_Workflow.json` | Ready-to-import n8n workflow |
| `docs/Setup_Instructions.txt` | Step-by-step setup guide |

## How to use

1. Import the JSON into your n8n instance
2. Connect OpenAI, Google Sheets, and Gmail credentials
3. Replace the placeholder Sheet ID and owner email
4. Point your website form to the webhook URL
5. Activate and test

Full setup instructions are in `docs/Setup_Instructions.txt`.

## Priority Logic

| Priority | When it is assigned |
|----------|---------------------|
| **HOT**  | Urgent language, higher budget, ready to start |
| **WARM** | Clear interest + some budget/timeline |
| **COLD** | Vague, no budget, low intent |

You can adjust the rules by editing the system prompt in the OpenAI node.

## Tech Stack

- n8n
- OpenAI (gpt-4o-mini recommended)
- Google Sheets
- Gmail

## Notes

- No real credentials are included
- All sensitive values are placeholders
- Safe to share and fork

---

Built as a practical lead automation example for digital marketing agencies.
