## Quick Overview

This workflow manually logs daily Gold and Silver prices from GoldAPI into Google Sheets, summarizes historical monthly averages, generates seasonal insights with Groq (LLM), builds QuickChart bar charts, and emails a formatted report via Gmail.

## How It Works

1. Starts manually and loads a two-item asset list (Gold/XAU and Silver/XAG) to process in a loop.
2. For each commodity, calls the GoldAPI endpoint to fetch the latest INR price and converts it into a per-10g value with date and month fields.
3. Checks Google Sheets for an existing row for the same commodity and date, keeps the higher of the two prices, and appends or updates the row in the historical sheet.
4. Reads the full historical dataset from Google Sheets and calculates monthly average, minimum, and maximum prices grouped by month and commodity.
5. Formats the monthly averages into a text block and sends it to a Groq-hosted chat model to generate a structured JSON insight summary for Gold, Silver, and the overall trend.
6. Creates QuickChart URLs for separate Gold and Silver monthly-average bar charts and emails the AI summary and chart images using Gmail.

## Requirements to Use This Workflow

- **[n8n account (Self-hosted or Cloud)](https://n8n.partnerlinks.io/om1efg2qgvwi)**
- **GoldAPI** account and API key
- **Google Sheets** account for storing historical commodity prices
- **Groq API** credentials for AI-generated seasonal insights
- **Gmail** account for sending automated reports
- Internet access to **QuickChart** for generating chart images

## Setup

1. Add a GoldAPI key and set it in the HTTP request header (`x-access-token`) for the GoldAPI call.
2. Connect Google Sheets OAuth credentials and select the target spreadsheet and sheet tab where rows are stored (for example, the `04_HistoricalData` sheet).
3. Ensure the sheet has columns for **ID**, **Date**, **Month**, **Price**, and **Commodity**, and that **ID** is used as the upsert/matching key.
4. Add Groq API credentials for the Groq chat model used to generate the JSON insights.
5. Connect Gmail OAuth credentials and replace the placeholder recipient address (`RECEIVER MAIL ID`) and email subject as needed.

## Need Help?

Need assistance implementing or extending this workflow? **WeblineIndia** can help you build scalable AI-powered commodity monitoring and reporting automations with n8n.

Our team can help you:

- Customize this workflow for precious metals, commodities, or financial markets.
- Integrate additional market data providers and APIs.
- Build advanced AI-powered reporting and forecasting workflows.
- Automate email reports, dashboards, and business notifications.
- Develop enterprise-grade n8n workflows tailored to your business requirements.

**Helpful Resources:**

- **Contact Us:** https://www.weblineindia.com/contact-us.html
- **n8n Automation Services:** https://www.weblineindia.com/n8n-automation/
- **Process Automation Solutions:** https://www.weblineindia.com/process-automation-solutions.html
- **Hire n8n Developers:** https://www.weblineindia.com/hire-n8n-developers/
