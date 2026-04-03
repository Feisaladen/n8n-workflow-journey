# n8n Workflow Journey

This repository documents my journey of learning n8n automation by building, testing, and improving real workflows week after week.

It is not just a storage repo for JSON exports. It is a learning log that shows what I built, how I structured it, and how my automation skills grow over time.

## Vision

The goal of this repository is to become a growing portfolio of n8n projects, experiments, and automation systems.

Each week adds a new piece of work. Over time, this repo should show:

- consistency in learning
- practical workflow building
- better project organization
- clearer documentation
- steady progress from simple automations to more advanced systems

## Learning Rhythm

I am using this repository as a 4-days-a-week learning system.

Each week is treated as a mini build cycle:

1. Day 1: Learn and explore a workflow idea
2. Day 2: Build the first working version in n8n
3. Day 3: Improve, test, or extend the workflow
4. Day 4: Document, clean up, and push the final work to this repository

This keeps the process structured and makes it easier to look back at progress week by week.

## How This Repo Is Organized

The root `README.md` is the main homepage of the repository.

Each week gets its own folder so that:

- workflow files do not clash
- README files stay specific to the project
- each build can be understood on its own
- future weeks can be added cleanly

## Folder Structure

```text
.
|-- README.md
|-- week-02/
|   |-- README.md
|   |-- crypto price logger.json
|   |-- Email summarizer.json
|   `-- Email summarizer README.md
|-- week-03/
|   |-- README.md
|   `-- workflow-file.json
`-- week-04/
    |-- README.md
    `-- workflow-file.json
```

## File Pattern For Each Week

Every weekly folder should ideally contain:

- `README.md`
  Explains the goal of that week's project, what the workflow does, tools used, setup steps, and key lessons.
- one or more workflow export files such as `workflow.json` or a descriptive file name
  Example: `crypto price logger.json`
- optional supporting files if needed
  Example: screenshots, notes, prompts, or test data

## Recommended Weekly Format

Use a structure like this for every new week:

```text
week-05/
|-- README.md
|-- main-workflow.json
|-- notes.txt
`-- assets/
```

## What Goes Inside A Weekly README

Each weekly README should answer these questions:

- What did I build this week?
- What problem does the workflow solve?
- Which n8n nodes or external services did I use?
- How does the workflow run step by step?
- What did I learn from building it?
- What would I improve next time?

## Weekly Projects

- [Week 02 - Crypto Price Logger](./week-02/README.md)
- [Week 02 - Email Summarizer](./week-02/Email%20summarizer%20README.md)

More weeks will be added as the journey continues.

## Why This Repository Matters

This repo helps me:

- track my automation journey in public
- stay disciplined with weekly output
- build a portfolio of n8n projects
- reflect on what I learn each week
- create proof of consistency and practical skill development

## Workflow For Adding A New Week

1. Create a new folder such as `week-03`
2. Export the n8n workflow into that folder
3. Add a `README.md` for that week's project
4. Keep file names clear and descriptive
5. Update this root README with the new week's link
6. Commit and push the changes

## Current Direction

The journey starts with simple automations like scheduled data logging and will grow into more advanced workflows involving APIs, alerts, integrations, AI tools, and business process automation.

## Repository Principle

One repository.
One ongoing learning journey.
One folder per week.
