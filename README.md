# zeotap-app2
Real-Time Weather Monitoring System
Overview
This project processes real-time weather data for Indian cities (Delhi, Mumbai, Chennai, Bangalore, Kolkata, Hyderabad) using the OpenWeatherMap API. It calculates daily temperature aggregates and sends alerts when user-defined thresholds are crossed.

Features
Real-time data retrieval every 5 minutes
Temperature conversion from Kelvin to Celsius
Daily summaries (average, max, min temperatures)
Threshold alerts for temperature and weather conditions
Database for storing summaries and thresholds

Clone the repository:
git clone https://github.com/your-username/weather-monitoring-system.git
cd weather-monitoring-system

Install dependencies:
pip install -r requirements.txt

Set your OpenWeatherMap API key in config.py:
API_KEY = "your_openweathermap_api_key"

Run the application:
python app.py

Temperature Conversion
def kelvin_to_celsius(kelvin_temp):
    return kelvin_temp - 273.15

# Example usage
temperature_kelvin = 300.0
temperature_celsius = kelvin_to_celsius(temperature_kelvin)
print(f"Temperature in Celsius: {temperature_celsius}")
Fetch Weather Data
import requests

def get_weather_data(city):
    url = f"http://api.openweathermap.org/data/2.5/weather?q={city}&appid={API_KEY}"
    response = requests.get(url)
    return response.json()

# Example usage
city = "Delhi"
weather_data = get_weather_data(city)
print(weather_data)
