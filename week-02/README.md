# Crypto Price Logger

This project contains an n8n workflow that fetches the current Bitcoin price in USD and logs it to Google Sheets on a schedule.

## What This Workflow Does

The workflow runs automatically every day at 9:00, requests the latest Bitcoin price from the CoinGecko API, formats the data, and appends a new row to a Google Sheet.

Each logged row includes:

- `date`
- `time`
- `btc_price`

## Workflow Overview

The exported workflow is named `crypto price logger` and uses these nodes:

1. `Schedule Trigger`
   Runs the workflow every day at 9:00.
2. `HTTP Request`
   Calls the CoinGecko API:
   `https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd`
3. `Edit Fields`
   Prepares the output fields:
   - `date` in `yyyy-MM-dd`
   - `time` in `HH:mm`
   - `btc_price` from the API response
4. `Append row in sheet`
   Adds the result to a Google Sheet.

## Example Output

Example row written to Google Sheets:

```text
date        time    btc_price
2026-03-30  09:00   82341
```

## File Included

- `crypto price logger.json` - the n8n workflow export

## Requirements

To use this workflow, you will need:

- An n8n instance
- A Google account connected to n8n through Google Sheets OAuth2 credentials
- A Google Sheet with these columns in the first row: `date`, `time`, `btc_price`
- Internet access for the CoinGecko API request

## How To Use

1. Open n8n.
2. Import `crypto price logger.json`.
3. Review the `Schedule Trigger` node and adjust the time if needed.
4. Open the Google Sheets node and connect your own Google Sheets credentials.
5. Replace the currently selected spreadsheet and sheet tab with your own target sheet.
6. Make sure the sheet contains the columns:
   `date`, `time`, `btc_price`
7. Save and activate the workflow.

## Google Sheet Setup

Create a sheet with a header row like this:

```text
date | time | btc_price
```

The workflow appends one new row on each run.

## Notes

- This workflow currently tracks only `bitcoin` in `usd`.
- The logged time is based on the time settings in your n8n environment.
- The exported workflow includes a preselected Google Sheet reference, so update that node before using it in your own account.
- If you publish this repository, review the exported workflow carefully before sharing it publicly, especially any linked spreadsheet references or credential-related metadata.

## Customization Ideas

You can extend this workflow to:

- Track more cryptocurrencies such as Ethereum or Solana
- Store prices in multiple currencies
- Send Telegram, Slack, or email alerts when the price changes sharply
- Build a dashboard from the Google Sheets data

## Suggested Repository Structure

```text
.
|-- README.md
`-- week-02/
    |-- README.md
    `-- crypto price logger.json
```

## License

Add a license if you plan to share or reuse this project publicly.
