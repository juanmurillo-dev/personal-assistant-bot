# Personal Assistant Bot 🤖

A fully automated personal assistant built with **N8N** and the **Telegram Bot API**, designed to manage workouts, study sessions, tasks, and personal finances — all from a single Telegram chat.

> Built independently as a personal productivity tool. All data is stored in **Google Sheets** as a lightweight database.

---

## Features

- **Workout Tracker** — Log training sessions with duration directly from Telegram
- **Study Session Tracker** — Track study time per subject for university
- **Personal Finance Manager** — Record income and expenses to monitor savings
- **Health Check** — Instant bot status verification with available command list

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| N8N | Workflow automation engine |
| Telegram Bot API | User interface & command handling |
| Google Sheets API | Data storage & logging |
| Railway | Cloud hosting (24/7, no local server needed) |

---

## How It Works

The bot listens for natural language commands via Telegram. Each message triggers an N8N workflow that parses the input, processes the data, and logs it to the corresponding Google Sheet.

```
User sends message → Telegram Bot API → N8N Workflow → Google Sheets
```

---

## Commands

| Command | Example | Description |
|---------|---------|-------------|
| `Hola` | `Hola` | Health check — verifies bot is online and lists available commands |
| `Entrene [minutes]` | `Entrene 45` | Logs a workout session with duration in minutes |
| `Estudie [hours] [subject]` | `Estudie 2h Matematicas` | Logs a study session for a specific subject |
| `Gasto [amount]` | `Gasto 15000` | Records an expense and updates savings log |
| `Ingreso [amount]` | `Ingreso 50000` | Records an income and updates savings log |

---

## Architecture

```
Telegram
    │
    ▼
N8N Webhook Trigger
    │
    ├── "Hola"        → Send welcome message + command list
    ├── "Entrene"     → Parse duration → Log to Workouts Sheet
    ├── "Estudie"     → Parse time + subject → Log to Study Sheet
    ├── "Gasto"       → Parse amount → Log to Finance Sheet
    └── "Ingreso"     → Parse amount → Log to Finance Sheet
```

---

## Data Storage

All data is stored in Google Sheets with the following structure:

- **Workouts Sheet** — Date, duration (minutes)
- **Study Sheet** — Date, subject, duration (hours)
- **Finance Sheet** — Date, type (income/expense), amount, running balance

---

## Deployment

This bot runs 24/7 on **Railway** cloud infrastructure at zero cost, with no local server required.

---

## About

Built by **Juan Pablo Murillo** — Systems Engineering student at Universidad Libre de Colombia.  
This project was built independently in the first semester of university as a real-world automation solution.

[![GitHub](https://img.shields.io/badge/GitHub-jpmurillo-181717?style=flat&logo=github)](https://github.com/jpmurillo)
