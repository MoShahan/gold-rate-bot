# 🛠️ Setup & Deployment Guide

This guide walks you through setting up the Telegram Bot, configuring GitHub Actions secrets, and deploying the script to run automatically every day.

---

## 📋 Prerequisites
- A **GitHub Account**.
- A **Telegram Account**.

---

## Step 1: Create a Telegram Bot
1. Open Telegram and search for [@BotFather](https://t.me/botfather).
2. Send the command `/newbot`.
3. Follow the prompts to enter a name and a username for your bot.
4. Copy the **API Token** provided (e.g., `123456789:ABCDefGhIJKlmNoPQRsTUVwxyZ`).

---

## Step 2: Get Your Telegram Chat ID(s)
1. Search for [@userinfobot](https://t.me/userinfobot) on Telegram and click **Start**.
2. Copy your numerical **Id** (e.g., `987654321`).
3. *(Optional)* If you want to send notifications to friends, ask them to message `@userinfobot` to get their IDs as well.

---

## Step 3: Configure GitHub Secrets
1. Go to your repository on **GitHub**.
2. Navigate to **Settings** > **Secrets and variables** > **Actions**.
3. Click **New repository secret** and add the following two items:

| Secret Name | Value Example | Notes |
| :--- | :--- | :--- |
| `TELEGRAM_TOKEN` | `123456789:ABCDefGh...` | The API Token from BotFather. |
| `TELEGRAM_CHAT_ID` | `987654321,123456789` | Your Chat ID(s). **Separate multiple IDs with commas** (no spaces). |

---

## Step 4: Repository File Structure

Ensure your repository contains the following structure:

```text
.
├── .github/
│   └── workflows/
│       └── daily_run.yml   # Workflow execution schedule
├── gold_scraper.py         # Main python scraper logic
├── requirements.txt        # Python dependencies
├── README.md               # Overview & features
└── SETUP.md                # Deployment instructions
