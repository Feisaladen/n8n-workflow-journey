# Email Summarizer

This project contains an n8n workflow that watches for new Gmail messages, summarizes them with Google Gemini, and sends the summary by email.

It is a simple example of using AI inside an automation flow to reduce inbox overload and turn raw email content into a short, readable update.

## What This Workflow Does

The workflow checks Gmail for new incoming emails, sends the subject, sender, and preview text to a Gemini chat model, then emails the generated summary to a chosen recipient.

The summary prompt asks the model to return:

1. What the email is about
2. Any action needed
3. How urgent it is

## Workflow Overview

The exported workflow is named `Email summarizer` and uses these nodes:

1. `Gmail Trigger`
   Polls Gmail every minute for new emails.
2. `Basic LLM Chain`
   Builds the summarization prompt using fields from the incoming email.
3. `Google Gemini Chat Model`
   Provides the AI model used by the LLM chain.
4. `Send a message`
   Sends the generated summary as an outgoing Gmail message.

## How The Workflow Runs

1. A new email is detected by the Gmail trigger.
2. The workflow collects key fields from that email:
   - `subject`
   - `from`
   - `snippet`
3. The `Basic LLM Chain` sends those values to Gemini with a prompt asking for a concise summary.
4. Gemini returns a short structured summary.
5. The Gmail node sends that summary to the configured email address.

## Prompt Used

The workflow uses a prompt with this intent:

- summarize clearly and concisely
- identify the main topic
- point out any required action
- estimate urgency

This makes the workflow useful for triaging messages quickly without reading the full email first.

## Example Output

Example summary email body:

```text
1. What the email is about:
The sender is following up on a meeting request for next Tuesday.

2. Any action needed:
Reply with your availability and confirm the time.

3. How urgent it is:
Medium urgency. A response today would be helpful.
```

## File Included

- `Email summarizer.json` - the n8n workflow export

## Requirements

To use this workflow, you will need:

- An n8n instance
- A Gmail account connected to n8n for the trigger and sending nodes
- Google Gemini credentials connected in n8n
- Permission to access the Gmail inbox you want to monitor
- A destination email address for receiving summaries

## Credentials Used

This workflow depends on:

- `gmailOAuth2`
  Used by both the Gmail trigger and the send-email node
- `googlePalmApi`
  Used by the Gemini chat model node

Before using the workflow in your own environment, replace any existing credential references with your own accounts.

## How To Use

1. Open n8n.
2. Import `Email summarizer.json`.
3. Open the `Gmail Trigger` node and connect your Gmail OAuth2 credential.
4. Review the polling settings and Gmail filters.
5. Open the `Google Gemini Chat Model` node and connect your Gemini API credential.
6. Open the `Send a message` node and replace the recipient email address with your own.
7. Test the workflow with a sample email.
8. Save and activate the workflow.

## Important Notes

- The current trigger checks for emails every minute.
- The workflow uses the Gmail `snippet`, which is usually only a preview of the email body, not always the full content.
- The outgoing summary is currently sent to a fixed email address, so you should change that before activating the workflow.
- Exported workflow files may include linked credential names, node metadata, or account references. Review them before sharing publicly.

## Limitations

- Summaries are only as good as the email data passed into the prompt.
- Because the workflow currently uses `snippet`, long or complex emails may be summarized from partial content.
- The workflow does not currently label, archive, or prevent duplicate handling beyond the trigger behavior.
- There is no extra validation step before the summary email is sent.

## Customization Ideas

You can improve this workflow by:

- sending summaries to Slack, Telegram, or Discord instead of email
- adding labels so only certain emails are summarized
- filtering by sender, subject, or category
- extracting full email content instead of only the snippet
- formatting the AI output as bullet points or JSON
- creating different prompts for support, sales, or personal emails
- storing summaries in Google Sheets or Notion for later review

## Suggested Repository Structure

```text
.
|-- README.md
`-- week-02/
    |-- README.md
    |-- crypto price logger.json
    |-- Email summarizer.json
    `-- Email summarizer README.md
```

## License

Add a license if you plan to share or reuse this project publicly.
