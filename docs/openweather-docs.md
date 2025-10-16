curl "https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY"
{
  "coord": {"lon": -0.1257, "lat": 51.5085},
  "weather": [{"id": 801, "main": "Clouds", "description": "few clouds"}],
  "main": {"temp": 288.55, "feels_like": 287.04},
  "name": "London"
}
| Parameter   | Type   | Required | Example      | Description                              |
| ----------- | ------ | -------- | ------------ | ---------------------------------------- |
| `q`         | string | Yes      | `London,uk`  | City name and optional country code      |
| `lat`/`lon` | float  | No       | `35`, `139`  | Latitude and longitude coordinates       |
| `units`     | string | No       | `metric`     | Units (`standard`, `metric`, `imperial`) |
| `appid`     | string | Yes      | YOUR_API_KEY | Unique API key                           |
| Parameter | Type   | Required | Example | Description         |
| --------- | ------ | -------- | ------- | ------------------- |
| `q`       | string | Yes      | `Paris` | City name           |
| `appid`   | string | Yes      | API key | Required for access |
curl "https://api.openweathermap.org/data/2.5/weather?q=Paris&appid=1234567890abcdef"
import requests

def get_weather(city, key):
    url = "https://api.openweathermap.org/data/2.5/weather"
    params = {"q": city, "appid": key, "units": "metric"}
    response = requests.get(url, params=params)
    return response.json()

print(get_weather("Tokyo", "YOUR_API_KEY"))
const fetch = require('node-fetch');

async function getWeather(city, key) {
  const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${key}&units=metric`;
  const res = await fetch(url);
  const data = await res.json();
  console.log(data);
}

getWeather("New York", "YOUR_API_KEY");
{
  "cod": 401,
  "message": "Invalid API key"
}
