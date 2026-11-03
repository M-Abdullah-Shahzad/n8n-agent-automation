# n8n Form Automation with CSV

This repository contains an importable n8n workflow named Form Automation with CSV. It reads rows from a CSV file, processes each record, submits a configured form request, evaluates the response, and records results in Google Sheets.

## Workflow overview

```text
Manual Trigger → Read CSV File → Extract CSV rows
→ Process items → Retrieve configured login page
→ Prepare configured challenge response → Submit login
→ Build form payload → Submit form → Check response
→ Success / Failure logging → Google Sheets
```

The export uses n8n file read/write, Extract from File, Code, HTTP Request, IF, and Google Sheets nodes.

## Import the workflow

1. Open your n8n instance.
2. Select Workflows → Import from File.
3. Choose Form Automation with CSV.json.
4. Review every node's file path, endpoint URL, request body, and field mapping before activating the workflow.

## Configuration checklist

- CSV file path and expected column names.
- Login and form submission URLs.
- Request headers and payload fields expected by your own application.
- Google Sheets credentials, spreadsheet, and worksheet.
- Output fields used to record successful and failed submissions.

Use n8n's credential store for authentication. Do not hardcode passwords, session cookies, API keys, or access tokens in workflow JSON.

## Run safely

- Test with a small CSV containing non-sensitive sample records first.
- Run only against systems you own or are explicitly authorized to automate.
- Follow the target service's terms, rate limits, and access-control requirements. Do not use this workflow to bypass CAPTCHA or other anti-abuse controls.
- Sanitize exported workflow files before committing them; n8n exports may contain sensitive configuration depending on export options.

## Repository contents

- Form Automation with CSV.json — n8n workflow export.
- README.md — setup, configuration, and safety notes.

## Limitations

This workflow is a template, not a turnkey integration. Endpoint URLs, CSV columns, form payloads, and Google Sheets credentials must be reviewed and configured for the intended authorized environment. A successful HTTP response does not by itself prove that a downstream business process completed correctly.

## License

No license is currently declared. Contact the repository owner before redistributing this workflow.