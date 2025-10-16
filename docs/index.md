<p align="center">
  <img src="./images/logo.png" width="180" alt="Logo"><br>
  <b>OpenWeatherMap REST API Documentation</b><br>
  <sub>by Yvette Ingram — Technical Writer & Developer Educator</sub>
</p>

---

## 📚 Table of Contents
- [Overview](#-overview)
- [Quick Start Example](#-quick-start-example)
- [Endpoints](#-endpoints)
- [Code Examples](#-code-examples)
- [Error Handling](#-error-handling)
- [Best Practices](#-best-practices)
- [Author](#-author)

---

## 🚀 Overview
The **OpenWeatherMap API** provides current and forecasted weather data for any city worldwide.  
It’s ideal for developers who need weather information for apps, dashboards, or IoT projects.

**Base URL:**


**Authentication:**  
All endpoints require an API key (`appid`) parameter.

**Base URL:**  https://api.openweathermap.org/data/2.5/
---

## ⚡ Quick Start Example
```bash
curl "https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY"

{
  "coord": {"lon": -0.1257, "lat": 51.5085},
  "weather": [{"id": 801, "main": "Clouds", "description": "few clouds"}],
  "main": {"temp": 288.55, "feels_like": 287.04},
  "name": "London"
}

---

## Endpoints

| Parameter   | Type   | Required | Example      | Description                         |
| ----------- | ------ | -------- | ------------ | ----------------------------------- |
| `q`         | string | Yes      | `London,uk`  | City name and optional country code |
| `lat`/`lon` | float  | No       | `35`, `139`  | Coordinates                         |
| `units`     | string | No       | `metric`     | Units of measurement                |
| `appid`     | string | Yes      | YOUR_API_KEY | Your personal API key               |


| Parameter | Type   | Required | Example  | Description  |
| --------- | ------ | -------- | -------- | ------------ |
| `q`       | string | Yes      | `Paris`  | City name    |
| `appid`   | string | Yes      | Required | Your API key |

---

## Code Examples

import requests

def get_weather(city, key):
    url = "https://api.openweathermap.org/data/2.5/weather"
    params = {"q": city, "appid": key, "units": "metric"}
    response = requests.get(url, params=params)
    return response.json()

print(get_weather("Tokyo", "YOUR_API_KEY"))

import fetch from "node-fetch";

async function getWeather(city, key) {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${key}&units=metric`;
  const res = await fetch(url);
  const data = await res.json();
  console.log(data);

## Error Handling

| Code | Meaning           | Description                   |
| ---- | ----------------- | ----------------------------- |
| 401  | Unauthorized      | Missing or invalid API key    |
| 404  | Not Found         | Invalid endpoint or city name |
| 429  | Too Many Requests | Rate limit exceeded           |

}

getWeather("New York", "YOUR_API_KEY");

{
  "cod": 401,
  "message": "Invalid API key"
}

---

##💡 Best Practices

Always use HTTPS for secure requests

Cache frequent responses to reduce API load

Use units and lang for localization

Store API keys securely (never expose client-side)

---

## 👤 Author

Yvette Ingram
Technical Writer & Software Developer
I combine writing clarity with technical depth to help developers build faster and learn smarter.

Connect with me:

💼 LinkedIn

🌐 Fiverr

🎥 YouTube

<p align="center"> <b>“Good documentation doesn’t just explain — it empowers.”</b> </p> ```
