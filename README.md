# 🏃‍♂️ TrailRun Advisor Agent

An AI-powered, weather-aware trail running assistant built using [n8n](https://n8n.io/). This project uses OpenAI, weather APIs, air quality data, and calendar integration to make real-time decisions about whether it's a good day for a trail run—and recommends the best trail accordingly.

This lightweight agent:
- Checks your calendar for a scheduled run
- Looks up real-time weather and air quality
- Evaluates local trail conditions from a spreadsheet
- Sends you a friendly email with a smart recommendation (or a heads-up if conditions aren’t ideal)

It’s a practical example of using agentic workflows and external tools to automate a personalized decision.

---

## 🌟 Overview

**TrailRun Advisor** is a smart AI agent that:
- Checks your calendar for a "Trail Run" event
- Assesses live air quality and weather conditions
- Reads local trail options from Google Sheets
- Filters trails based on time, elevation, and shade level
- Sends you a friendly email with the best trail recommendation (or a reason not to go)

---

## 📸 Preview

<img width="766" alt="image" src="https://github.com/user-attachments/assets/0baf5709-ead8-4a57-ada3-ac28e7c900c6" />

---

## 🧠 How It Works

The core logic is handled by an **AI Agent in n8n**, powered by OpenAI and orchestrated using custom tools:

| Tool           | Purpose                                        |
|----------------|------------------------------------------------|
| `checkCalendar` | Fetch today's events from Google Calendar     |
| `getWeather`    | Get current temperature and sunlight conditions |
| `getAirQuality` | Check PM2.5 AQI using a public API            |
| `getHikeList`   | Load local trails (distance, elevation, shade) |
| `sendEmail`     | Send a summary message with the trail recommendation |

The prompt logic ensures the agent only recommends a trail when the weather and air quality are favorable, and selects one that matches your schedule and environment preferences.

---

## 🔧 Tech Stack

- **n8n** – Low-code workflow automation
- **OpenAI** – Natural language reasoning
- **Google Sheets** – Trail data storage
- **Gmail API** – Send personalized trail run recommendations
- **Google Calendar API** – Check for scheduled runs
- **AirNow API** – Air quality information
- **Weather API** – Live weather for your location (Bloomington, IN)

---

## 🚀 Running the Project

1. **Clone this repo**
2. **Import `n8n-workflow.json`** into your n8n instance
3. Connect the following credentials:
   - Google (Sheets, Calendar, Gmail)
   - OpenAI
   - Weather & Air Quality API (API key)
4. Update your trail data in `Google Sheets` (sample in `/sample-data/hikeList.csv`)
5. Set a recurring event titled `"Trail Run"` in your calendar
6. Trigger the workflow via schedule or test manually

---

## ✨ Example Email Output

![image](https://github.com/user-attachments/assets/005c2489-3064-4546-a632-f81fcf90674d)


