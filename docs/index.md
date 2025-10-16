# 🌤️ OpenWeatherMap REST API Documentation

Welcome to the **OpenWeatherMap API Documentation** — a sample project showcasing how to write and publish clear, developer-friendly documentation using Markdown and GitHub Pages.

This example demonstrates:
- How to document RESTful APIs  
- How to structure technical documentation for readability  
- How to combine code samples and best practices into one cohesive guide  

---

## 🚀 Overview
The **OpenWeatherMap API** provides current and forecasted weather data for cities across the world.  
To access it, you need a free API key from [https://openweathermap.org/api](https://openweathermap.org/api).

**Base URL:**
https://api.openweathermap.org/data/2.5/

**Authentication:**
All requests require an API key parameter `appid`.

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

## ⚡ Endpoints
/weather

| Parameter   | Type   | Required | Example      | Description                         |
| ----------- | ------ | -------- | ------------ | ----------------------------------- |
| `q`         | string | Yes      | `London,uk`  | City name and optional country code |
| `lat`/`lon` | float  | No       | `35`, `139`  | Coordinates for location            |
| `units`     | string | No       | `metric`     | Units of measurement                |
| `appid`     | string | Yes      | YOUR_API_KEY | Your personal API key               |

/forecasts

| Parameter | Type   | Required | Example  | Description  |
| --------- | ------ | -------- | -------- | ------------ |
| `q`       | string | Yes      | `Paris`  | City name    |
| `appid`   | string | Yes      | Required | Your API key |


## ⚡ Code Examples
/python
import requests

def get_weather(city, key):
    url = "https://api.openweathermap.org/data/2.5/weather"
    params = {"q": city, "appid": key, "units": "metric"}
    response = requests.get(url, params=params)
    return response.json()

print(get_weather("Tokyo", "YOUR_API_KEY"))

/JavaScript (Node.js)
javascript

import fetch from "node-fetch";

async function getWeather(city, key) {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${key}&units=metric`;
  const res = await fetch(url);
  const data = await res.json();
  console.log(data);
}

getWeather("New York", "YOUR_API_KEY");

## ⚡ Error Handling

| Code | Meaning           | Description                   |
| ---- | ----------------- | ----------------------------- |
| 401  | Unauthorized      | Invalid or missing API key    |
| 404  | Not Found         | Invalid endpoint or city name |
| 429  | Too Many Requests | Rate limit exceeded           |

Example Error Response
/json

{
  "code": 401,
  "message": "Invalid API key"
}

