1. Overview

The OpenWeatherMap API provides weather data for cities around the globe.

Base URL: https://api.openweathermap.org/data/2.5/

Authentication: Requires an API key (appid).

Formats: JSON or XML.

2. Quick Start

Here’s how to make your first API call:

curl "https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY"


Response (JSON):

{
  "coord": {"lon": -0.1257, "lat": 51.5085},
  "weather": [{"id": 801, "main": "Clouds", "description": "few clouds"}],
  "main": {"temp": 288.55, "feels_like": 287.04},
  "name": "London"
}

3. Endpoints
🔹 Current Weather

GET /weather
Retrieve current weather data for a city.

Parameter	Type	Required	Example	Description
q	string	Yes	London,uk	City name and optional country code
lat/lon	float	No	35, 139	Latitude and longitude coordinates
units	string	No	metric	Units (standard, metric, imperial)
appid	string	Yes	YOUR_API_KEY	Unique API key
🔹 5-Day Forecast

GET /forecast
Retrieve weather forecast data in 3-hour intervals.

Parameter	Type	Required	Example	Description
q	string	Yes	Paris	City name
appid	string	Yes	API key	Required for access
4. Authentication

All endpoints require an API key:

curl "https://api.openweathermap.org/data/2.5/weather?q=Paris&appid=1234567890abcdef"

5. Code Examples
Python
import requests

def get_weather(city, key):
    url = "https://api.openweathermap.org/data/2.5/weather"
    params = {"q": city, "appid": key, "units": "metric"}
    response = requests.get(url, params=params)
    return response.json()

print(get_weather("Tokyo", "YOUR_API_KEY"))

JavaScript (Node.js)
const fetch = require('node-fetch');

async function getWeather(city, key) {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${key}&units=metric`;
  const res = await fetch(url);
  const data = await res.json();
  console.log(data);
}

getWeather("New York", "YOUR_API_KEY");

6. Error Handling

Example of invalid API key:

{
  "cod": 401,
  "message": "Invalid API key"
}


Common Errors:

401 Unauthorized: Missing or invalid API key

404 Not Found: Invalid endpoint or city name

429 Too Many Requests: Rate limit exceeded

7. Best Practices

Always use HTTPS for secure requests.

Cache responses to avoid exceeding rate limits.

Use units and lang parameters to localize results.
