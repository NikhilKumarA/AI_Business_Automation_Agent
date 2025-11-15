# AI_Business_Automation_Agent
AI-powered automation system for small grocery shops: product search, pricing, cart management, invoice (PDF) generation, and daily sales logging using Python.
AI Business Automation Agent (Python)

An end-to-end automation tool designed for small grocery shops to handle product search, cart management, billing, PDF invoice generation, and daily sales logging — built using Python and Google Colab.

This project demonstrates real-world automation useful for kirana/grocery stores that still rely on manual billing.

Features Implemented (Phase 1 + Phase 2)
1. Product Search (Partial + Exact Match)

Search items by exact name

Search using partial match (e.g., "mil" → "milk")

Token-based fuzzy matching

Powered by pandas string filters

2. Rule-Based Assistant

Understands natural commands like:

"price of rice"

"find sugar"

"add 2 rice"

"show cart"

Handles search, pricing, adding items, showing cart, etc.

3. Cart Management

Add items using SKU + quantity

Auto-calculates line totals

Shows cart in clean table format (GitHub-style table) using tabulate

4. Billing System

Automatically calculates total bill

Stores cart items with quantity and price

5. PDF Invoice Generation

Creates a professional invoice (PDF)

Includes:

Shop name

Invoice ID

Timestamp

Product table

Quantity, price, totals

Saved inside /outputs/

6. Daily Sales Logging

Appends each bill to outputs/sales_log.csv

Stores:

Invoice ID

Total amount

PDF filename

Timestamp

📂 Project Structure
📦 ai-business-automation-agent
 ┣ 📂 data
 ┃ ┗ 📄 products.csv
 ┣ 📂 outputs
 ┃ ┣ 📄 bill_<id>.pdf
 ┃ ┗ 📄 sales_log.csv
 ┣ 📄 AI_Business_Automation_Agent.ipynb
 ┣ 📄 README.md
 ┗ 📄 .gitignore

How the Assistant Works
Example:

User:

price of rice


Assistant:

Reads CSV

Performs string match

Returns product + price

Example:

User:

add 2 rice


Assistant:

Finds product → SKU

Adds to cart

Updates line total

Example:

User:

show cart


Assistant:

Displays table

Shows total

Example:

User:

checkout


Assistant:

Generates PDF

Logs sale

Clears cart

🧾 Sample Output (Cart Table)
|   # | Product   | SKU       |   Qty | Unit   |   Price |   LineTotal |
|----:|-----------|-----------|-------|--------|---------|-------------|
|   1 | rice      | RICE_001  |     2 | kg     |      45 |          90 |
|   2 | milk      | MLK_001   |     1 | litre  |      25 |          25 |

Invoice PDF Example

Each generated PDF includes:

Shop name (editable)

Invoice number

Date and time

Clean tabular layout

Total amount

PDFs are saved automatically in:

/outputs/bill_<invoice_id>_<timestamp>.pdf

Daily Sales Logging

Each purchase appends a row to:

outputs/sales_log.csv


With:

invoice_id

total

file (PDF path)

timestamp

This can be used later for monthly or daily sales reports.

Technologies Used

Python 3

Pandas — Data operations

Tabulate — Cart table formatting

ReportLab — PDF invoice generation

Google Colab — Development environment

How to Run (Google Colab)
Option A — Run directly in Colab

Open the notebook (AI_Business_Automation_Agent.ipynb)

Upload data/products.csv if needed

Run all cells

Use assistant commands to test

Generate PDF invoices automatically

How to Run Locally (Python)

Clone the repo:

git clone https://github.com/<your-username>/ai-business-automation-agent.git


Install dependencies:

pip install pandas reportlab tabulate


Run example code inside the notebook or port to a .py file.
