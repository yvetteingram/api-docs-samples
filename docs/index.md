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

{
  "coord": {"lon": -0.1257, "lat": 51.5085},
  "weather": [{"id": 801, "main": "Clouds", "description": "few clouds"}],
  "main": {"temp": 288.55, "feels_like": 287.04},
  "name": "London"
}


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

<p align="center">
  <b>Created by [Your Name]</b><br>
  <a href="https://www.linkedin.com/in/drerinjacques/">LinkedIn</a> • 
  <a href="https://www.fiverr.com/">Fiverr</a> • 
  <a href="https://www.youtube.com/@Dr.ErinJacques">YouTube</a>
</p>
