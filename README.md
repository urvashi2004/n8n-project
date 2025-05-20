# README: Welcome Email Automation Workflow (n8n)

## Overview

This workflow automates generating personalized welcome emails using the Meta LLaMA-3 API and updates a Google Sheet with the generated content and status.

---

## How to Import the Workflow

1. Open your n8n editor.
2. Click on **Workflows > Import**.
3. Select the provided `SheetsWorkslow.json` export file.
4. The workflow will be loaded into your workspace.

---

## Credentials and API Keys Setup

- **Google Sheets Credential:**
  - Go to **Settings > API Credentials** in n8n.
  - Create or add a Google Sheets OAuth2 credential with access to your target spreadsheet.
  - Assign this credential to the Google Sheets nodes in the workflow.

- **OpenRouter / Meta LLaMA API Credential:**
  - Obtain your API Bearer token from OpenRouter or Meta LLaMA.
  - In the HTTP Request node, set the Authorization header as:  
    `Authorization: Bearer YOUR_API_KEY`
  - Replace `YOUR_API_KEY` with your actual API key.

---

## Running and Testing the Workflow

- Ensure the Google Sheet is shared with the service account/email used in your Google Sheets credential.
- Trigger the workflow manually or via your preferred trigger node.
- The workflow reads rows from the sheet where `status` is `not-sent`, sends the name to the LLaMA API to generate a welcome email, then updates the row with the email content and changes status to `sent`.
- Check your Google Sheet after execution to verify the updated rows.

---

## Deliverables

- **Google Sheet link:** [Insert your public view-only Google Sheet URL here]  
- **Exported workflow:** See attached `.json` export file  
- **Successful execution screenshot:** See attached `.png` or `.jpg`

---

If you have any questions or need help setting this up, feel free to ask!
