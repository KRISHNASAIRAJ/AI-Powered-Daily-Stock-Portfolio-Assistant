# 📊 AI-Powered Daily Portfolio Assistant (n8n Automation)

An **AI-driven portfolio monitoring system** that automatically analyzes stock holdings, evaluates market sentiment, and delivers a **daily investment report directly to Slack**.

Built using **n8n, Google Gemini AI, Google Sheets, and NSE APIs**, this automation eliminates manual portfolio tracking and provides **smart daily insights.**

---

# 🚀 Project Overview

This project automates the entire process of **portfolio monitoring and daily analysis**.

Every day at **7 PM**, the workflow automatically:

1. Fetches portfolio data from **Google Sheets**
2. Retrieves **FII/DII institutional activity** from NSE India
3. Calculates portfolio metrics like:
   - Net worth
   - Total investment
   - Unrealized profit/loss
4. Uses **Google Gemini AI** to analyze portfolio performance
5. Generates a **concise AI investment report**
6. Sends the report to **Slack**

This transforms a simple spreadsheet portfolio into an **intelligent automated portfolio assistant**.

---

# 🧠 Problem Statement

Most investors track their portfolio manually by:

- Checking stock prices
- Calculating profits/losses
- Monitoring market news
- Reviewing institutional activity

This process is **time-consuming and repetitive**.

Additionally, combining **portfolio data with market sentiment** requires multiple tools and manual analysis.

### Key Challenges

• Manual portfolio monitoring  
• Lack of automated insights  
• No integration between portfolio data and market activity  
• Time wasted analyzing spreadsheets daily  

---

# 💡 Solution

Below is the visual representation of the n8n automation workflow.

![n8n Workflow](https://github.com/KRISHNASAIRAJ/AI-Powered-Daily-Stock-Portfolio-Assistant/blob/main/Workflow.jpeg)

This workflow automates portfolio monitoring by combining:

• **Portfolio Data (Google Sheets)**  
• **Market Data (NSE API)**  
• **AI Analysis (Google Gemini)**  
• **Automated Notifications (Slack)**  

The system generates **a daily AI-powered portfolio report** automatically.

---

# 🏗 Solution Architecture
Daily Schedule Trigger (7 PM)
          │
          ▼
Fetch Portfolio Data (Google Sheets)
          │
          ▼
Fetch Institutional Data (NSE API)
          │
          ▼
Process Portfolio Metrics (Code Node)
          │
          ▼
Process FII/DII Market Data
          │
          ▼
Merge Portfolio + Market Data
          │
          ▼
AI Analysis using Google Gemini
          │
          ▼
Generate Insight Report
          │
          ▼
Send Daily Report to Slack


---

# ⚙ Workflow Flow (Step-by-Step)

## 1️⃣ Daily Schedule Trigger

Runs the automation **every day at 7 PM IST**.

Purpose:
- ensures automated execution
- no manual intervention required

---

## 2️⃣ Portfolio Data (Google Sheets)

Reads stock portfolio data stored in Google Sheets.

Example structure:

| Name | Sector | Industry | Holding Units | Buy Price | CMP | Day Change |
|-----|-----|-----|-----|-----|-----|-----|

This sheet acts as the **portfolio database**.

---

## 3️⃣ NSE Institutional Data API

Fetches **FII/DII institutional activity** from NSE.

API used: https://www.nseindia.com/api/fiidiiTradeReact


This provides:

- Foreign Institutional Investor (FII) flow
- Domestic Institutional Investor (DII) flow
- Market sentiment

---

## 4️⃣ Portfolio Metrics Processing

A **JavaScript Code Node** processes the portfolio data.

It calculates:

- Current Value
- Total Investment
- Unrealized Profit/Loss
- Net Worth
- REIT Exposure

Example calculations:
Current Value = CMP × Quantity
Investment = Buy Price × Quantity
Profit/Loss = Current Value − Investment


---

## 5️⃣ Institutional Flow Processing

Another **Code Node** extracts:

- FII net flow
- DII net flow
- Net institutional flow

Formula:
Net Flow = FII + DII


---

## 6️⃣ Data Formatting (Merge Node)

Portfolio metrics and institutional data are merged into **one dataset**.

This dataset is passed to the AI assistant.

---

## 7️⃣ AI Portfolio Analysis (Google Gemini)

Google Gemini analyzes:

• daily stock performance  
• portfolio concentration risk  
• institutional market sentiment  
• portfolio profitability  

The AI produces a **short investment summary**.

---

## 8️⃣ Merge AI Report + Portfolio Data

The AI report is combined with:

- portfolio metrics
- market data

This creates the **final report payload**.

---

## 9️⃣ Slack Notification

The final formatted report is sent to Slack.

Example Slack message:
📅 Daily Portfolio Report — 2026-03-11

💼 Portfolio Overview
💰 Total Investment: ₹3,40,000
📊 Current Value: ₹3,78,200
📈 Unrealized P&L: ₹38,200
🏢 REIT Exposure: ₹40,000

📊 Institutional Activity
🟢 DII Net Buying: ₹1200 Cr
🔴 FII Net Selling: ₹-950 Cr
⚖️ Net Flow: ₹250 Cr

🤖 AI Portfolio Insight

🏆 Best Performer Of The Day
TCS gained +2.3%

📉 Worst Performer Of The Day
HDFC Bank declined -1.8%

⚠ Risk / Concentration
Portfolio heavily concentrated in banking sector.

📈 Market Context
Domestic institutional buying indicates positive market support.

📊 Portfolio Summary
Portfolio remains profitable with strong IT sector performance.

---

# 🛠 Technologies Used

| Technology | Purpose |
|---|---|
| **n8n** | Workflow automation |
| **Google Sheets API** | Portfolio data storage |
| **NSE India API** | Market institutional data |
| **Google Gemini AI** | AI-powered portfolio insights |
| **Slack API** | Daily report notifications |
| **JavaScript** | Data processing |
| **HTTP API** | External data fetching |

---

# ✨ Key Features

### 📊 Automated Portfolio Calculations
Automatically calculates:

- net worth
- total investment
- unrealized P&L

### 🤖 AI Portfolio Insights
Google Gemini generates **daily investment summaries**.

### 📈 Market Sentiment Analysis
Uses **FII/DII flows** to understand institutional market behavior.

### 📬 Automated Notifications
Daily reports are delivered directly to **Slack**.

### ⚠ Portfolio Risk Detection
Highlights **sector concentration risk**.

### ⏱ Fully Automated System
Runs automatically every day.

---
