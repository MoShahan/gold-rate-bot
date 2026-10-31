# 🪙 Kerala Daily Gold Rate Bot

An automated Python scraper that fetches daily gold rates (22K and 18K) from the **All Kerala Gold & Silver Merchants Association (AKGSMA)** and broadcasts them directly to Telegram.

---

## 🚀 Features
- **Live Scraping:** Fetches official daily rates directly from [AKGSMA](https://akgsma.com/).
- **Multi-Karat & Unit Tracking:** Calculates 1 gram and 8 gram (1 Pavan) prices for **22K** gold.
- **Dynamic Date Ingestion:** Formats daily alerts automatically with current date tags (`DD/MM/YYYY`).
- **Multi-User Broadcast:** Broadcasts updates to single or multiple chat IDs in parallel.
- **100% Serverless & Free:** Automated using GitHub Actions and the Telegram Bot API.

---

## 🛠️ Tech Stack
- **Language:** Python 3.10
- **Scraping & Requests:** `BeautifulSoup4`, `requests`
- **CI/CD & Scheduled Cron:** GitHub Actions (YAML)
- **Notification API:** Telegram Bot API

---

## 🤖 How It Works
1. **Trigger:** A scheduled GitHub Actions cron job wakes up every morning at **09:00 AM IST** (`30 3 * * *` UTC).
2. **Extraction:** The script parses HTML elements on the AKGSMA site, targeting `22K916 (1gm)`.
3. **Parsing & Formatting:** Cleans non-numeric noise, computes the 8-gram (Pavan) values, formats values with Indian numeric separators (`₹XX,XXX`), and attaches the current date.
4. **Broadcast:** Sends the formatted message iteratively to all recipient Chat IDs stored securely in GitHub Secrets.

---

## 📈 Example Notification

✨ **Kerala Gold Rate - 15/02/2026**

🟡 **22K Gold (916)**
• 1 gram: ₹14,460
• 8 gram: ₹115,680

📍 Source: AKGSMA

---

## 📖 Setup & Deployment Instructions
To recreate this bot and deploy it for your own use, follow the detailed step-by-step guide in [SETUP.md](SETUP.md).

---
*Created with ❤️ for personal use in Kerala.*
