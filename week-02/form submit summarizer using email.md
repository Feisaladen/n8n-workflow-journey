# Form Submit Summarizer Using Email

This n8n workflow automates the collection of student interest forms for a Software Development Cohort and provides daily email summaries to administrators.

## Workflow Overview

The workflow consists of two main parts:

### 1. Form Submission Collection
- **Trigger**: Form submission via n8n's built-in form trigger
- **Form Fields**:
  - Full Name (required)
  - Phone Number (number, required)
  - Email Address (email)
- **Action**: Automatically appends new submissions to a Google Sheets spreadsheet

### 2. Daily Email Summary
- **Trigger**: Scheduled to run daily at 8:00 AM
- **Process**:
  1. Retrieves all current submissions from the Google Sheet
  2. Sends the data to OpenRouter AI for summarization
  3. Generates a professional morning briefing report
  4. Emails the summary to the admin team

## Key Features

- **Automated Data Collection**: No manual intervention needed for form submissions
- **Centralized Storage**: All data stored in Google Sheets for easy access
- **AI-Powered Summarization**: Uses OpenRouter's AI to create human-like, professional reports
- **Scheduled Reporting**: Daily morning briefings help admins stay updated
- **Professional Communication**: Warm, professional tone in all communications

## Configuration

### Required Credentials
- Google Sheets OAuth2 API (for spreadsheet access)
- Gmail OAuth2 (for sending summary emails)
- OpenRouter API Key (for AI summarization)

### Google Sheet Setup
- Document ID: `1E8-ZDJAmkTZGtRTZsSZU-tHgLnhQcJnm0U62TZq42To`
- Sheet Name: `Sheet1` (gid=0)
- Columns: Full name, phone number, Email address

### Email Configuration
- Recipient: feisaladen32@gmail.com
- Subject: "Morning Briefing - software Dev Cohort Submission"

## AI Prompt Details

The workflow uses this prompt for summarization:

```
You are a helpful admin assistant supporting an educational institution. Review these student interest submissions for the upcoming Software Development Cohort and prepare a brief, well-structured morning report for the admin team. Keep the tone warm, professional and human. Highlight the total number of interested students, list their names and contact details clearly, and close with a short note to help the team plan their day.

Here are today's submissions:
[List of submissions with Name, Phone, Email]
```

## Usage

1. Activate the workflow in n8n
2. Share the form URL with potential students
3. The workflow will automatically handle submissions
4. Daily at 8 AM, admins will receive email summaries

## Dependencies

- n8n (workflow automation platform)
- Google Sheets API
- Gmail API
- OpenRouter AI API