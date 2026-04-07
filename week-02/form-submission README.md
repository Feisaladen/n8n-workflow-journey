# Form Submission Logger

This project contains an n8n workflow that collects responses from a hosted form and stores each submission in Google Sheets.

It is a simple example of using n8n forms to capture interest for a program or event and automatically keep the responses organized in a spreadsheet.

## What This Workflow Does

The workflow displays an interest form for a software development cohort. When someone submits the form, n8n captures the response and appends the submitted details to a Google Sheet.

The form currently collects:

- `Full Name`
- `phone number`
- `email address`

## Workflow Overview

The exported workflow is named `form-submission` and uses these nodes:

1. `On form submission`
   Hosts the form and waits for a user to submit their details.
2. `Append row in sheet`
   Writes each submitted response to Google Sheets.

## How The Workflow Runs

1. A user opens the form titled `software Development cohort interest form`.
2. The user enters their name, phone number, and optional email address.
3. When the form is submitted, the `On form submission` node captures the values.
4. The Google Sheets node appends a new row to the target spreadsheet.

## Form Details

The form is configured with:

- Title: `software Development cohort interest form`
- Description: `register your interest for the next software development cohort`

Fields included:

- `Full Name` - required
- `phone number` - required
- `email address` - optional

## Data Stored In Google Sheets

The workflow maps the submitted form values into these sheet columns:

- `Full name`
- `phone number`
- `Email address`

## Example Output

Example row written to Google Sheets:

```text
Full name      phone number   Email address
Jane Doe       254700123456   jane@example.com
```

## File Included

- `form-submission.json` - the n8n workflow export

## Requirements

To use this workflow, you will need:

- An n8n instance
- Access to n8n Forms
- A Google account connected to n8n through Google Sheets OAuth2 credentials
- A Google Sheet with matching columns in the first row:
  `Full name`, `phone number`, `Email address`

## Credentials Used

This workflow depends on:

- `googleSheetsOAuth2Api`
  Used by the Google Sheets node to append submissions

Before using the workflow in your own environment, replace any existing credential references with your own account.

## How To Use

1. Open n8n.
2. Import `form-submission.json`.
3. Open the `On form submission` node and review the form title, description, and fields.
4. Open the `Append row in sheet` node and connect your own Google Sheets credential.
5. Replace the currently selected spreadsheet and sheet tab with your own target sheet.
6. Make sure your sheet header row contains:
   `Full name`, `phone number`, `Email address`
7. Test the form by submitting a sample entry.
8. Save and activate the workflow.

## Notes

- The phone number field is currently set as a number field.
- The email field is optional in the current form setup.
- The exported workflow includes a preselected spreadsheet reference, so you should change it before using the workflow in your own account.
- Exported workflow files may include linked credential names, node metadata, or spreadsheet references. Review them before sharing publicly.

## Limitations

- There is no validation beyond the form field configuration.
- The workflow only stores submissions in Google Sheets and does not send any confirmation email or notification.
- Phone numbers stored as numbers may lose formatting such as leading zeros depending on sheet settings.

## Customization Ideas

You can extend this workflow by:

- sending a confirmation email after each submission
- notifying a team in Slack, Telegram, or WhatsApp
- adding more fields such as experience level, preferred schedule, or location
- validating phone number format before saving
- tagging leads in a CRM or storing responses in Airtable or Notion

## Suggested Repository Structure

```text
.
|-- README.md
`-- week-02/
    |-- README.md
    |-- crypto price logger.json
    |-- Email summarizer.json
    |-- Email summarizer README.md
    |-- form-submission.json
    `-- form-submission README.md
```

## License

Add a license if you plan to share or reuse this project publicly.
