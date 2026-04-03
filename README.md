# n8n Workflow Journey

This repository documents an ongoing hands-on journey of learning n8n by building real workflows, improving them over time, and documenting what each workflow does.

It is both a learning log and a portfolio. Instead of only storing exported JSON files, this repo explains the purpose of each workflow, the tools involved, and the lessons learned from building them.

## What This Repository Is About

The goal of this project is to grow from simple automations into more practical and advanced workflow systems.

Each week adds a new build, experiment, or improvement. Over time, this repository should show:

- consistent practice with n8n
- practical automation ideas turned into working workflows
- better documentation and project structure
- growing confidence with APIs, triggers, AI tools, and integrations
- visible progress from beginner-friendly flows to more advanced solutions

## Why This Repository Exists

This repo helps me:

- track my progress publicly
- stay disciplined with a weekly building habit
- build a portfolio of real automation work
- reflect on what I am learning in a structured way
- create proof of consistency and practical skills over time

## Learning Approach

I am treating this repository as a weekly build system rather than a random collection of files.

Each week follows a simple rhythm:

1. Explore an idea or use case
2. Build the first working version in n8n
3. Improve, test, or extend the workflow
4. Document the result and commit it to the repo

This process makes the journey easier to sustain and easier to review later.

## Repository Structure

The root `README.md` acts as the main homepage.

Each weekly folder contains one or more workflow exports plus supporting documentation so that every workflow can be understood on its own.

```text
.
|-- README.md
`-- week-02/
    |-- README.md
    |-- crypto price logger.json
    |-- Email summarizer.json
    `-- Email summarizer README.md
```

## What Goes In Each Week Folder

Each weekly folder should ideally contain:

- `README.md`
  A summary of the week's work, learning outcomes, setup notes, and workflow explanations
- one or more exported workflow files
  Example: `crypto price logger.json`
- optional supporting files
  Example: notes, screenshots, prompts, sample data, or assets

Recommended pattern:

```text
week-05/
|-- README.md
|-- main-workflow.json
|-- extra-workflow.json
|-- notes.txt
`-- assets/
```

## Current Workflows

### Week 02

- [Week 02 Overview](./week-02/README.md)
  Contains the current week folder summary and links to workflow files
- [Crypto Price Logger](./week-02/README.md)
  A scheduled workflow that fetches the Bitcoin price from CoinGecko and logs it to Google Sheets
- [Email Summarizer](./week-02/Email%20summarizer%20README.md)
  A Gmail-based workflow that uses Google Gemini to summarize incoming emails and send the summary by email

More weeks will be added as the journey continues.

## Workflow Themes In This Repository

The workflows in this repository may include:

- scheduled automations
- API integrations
- data logging and reporting
- email-based workflows
- AI-assisted summarization or classification
- business process automation experiments

As the repository grows, the workflows should become more reliable, more modular, and more useful in real-world scenarios.

## Tools And Services Used

Depending on the workflow, projects in this repo may use:

- n8n
- Gmail
- Google Sheets
- HTTP Request integrations
- CoinGecko API
- Google Gemini
- future messaging, database, webhook, and AI services

## How To Use A Workflow From This Repo

If you want to reuse one of the workflows:

1. Open n8n.
2. Import the workflow JSON file from the relevant week folder.
3. Review all credentials before activation.
4. Replace any linked accounts, sheets, emails, or API settings with your own.
5. Test the workflow with safe sample data.
6. Activate it only after confirming the configuration works as expected.

## Important Safety Notes

- Exported n8n workflow files can contain credential names, selected resources, metadata, and account references.
- Always review workflows before sharing them publicly.
- Replace recipient emails, spreadsheet references, and connected services with your own before activating imported workflows.
- When using AI nodes, review prompts and outputs carefully so automations do not send inaccurate or unwanted results.

## Documentation Standard For This Repo

Each workflow README should try to answer:

- What was built?
- What problem does it solve?
- Which nodes or services are used?
- How does the workflow run step by step?
- What setup is required?
- What did I learn from building it?
- What would I improve next time?

This keeps the repository readable for both future me and anyone else exploring the work.

## Workflow For Adding A New Week

1. Create a folder such as `week-03`.
2. Export the workflow JSON into that folder.
3. Add a clear `README.md` for the week or for the workflow if needed.
4. Keep file names descriptive and easy to understand.
5. Update the root README with the new project link.
6. Commit and push the changes.

## Current Direction

The journey currently starts with simple automations such as scheduled logging and AI-assisted email handling.

The long-term direction is to build toward more advanced systems involving:

- richer API integrations
- alerts and notifications
- AI-powered decision support
- internal workflow automation
- reusable automation templates
- better error handling and operational reliability

## Repository Principle

One repository.
One learning journey.
One growing collection of practical n8n workflows.
