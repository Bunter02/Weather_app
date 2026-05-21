🌤️ Python Weather App
A simple command-line weather app that shows today's and tomorrow's forecast for any city in the world. No API key or account required.

Features

Fetches live weather data for any city
Shows today's and tomorrow's forecast
Displays high/low temperatures and weather description
Free to use — powered by Open-Meteo and OpenStreetMap


Requirements

Python 3.8 or higher
requests
geopy


Installation
1. Clone or download this repository, then navigate to the project folder:
bashcd path/to/your/project
2. Install dependencies:
bashpython -m pip install requests geopy

Usage
Run the script from your terminal or PowerShell:
bashpython weather.py
You will be prompted to enter a city name:
Enter a city: London
Today (2026-05-21): Partly cloudy
  High: 18°C  Low: 11°C

Tomorrow (2026-05-22): Light rain
  High: 15°C  Low: 9°C

How It Works

City → Coordinates — geopy uses the Nominatim geocoder (OpenStreetMap) to convert the city name into a latitude and longitude.
Coordinates → Forecast — The Open-Meteo API returns daily max/min temperature and a WMO weather code for the next 2 days.
Weather code → Description — A dictionary maps WMO codes to human-readable descriptions (e.g. 61 → "Light rain").


APIs Used
ServicePurposeCostOpen-MeteoWeather forecast dataFree, no key neededNominatim (OpenStreetMap)City → coordinates lookupFree, no key needed

Project Structure
weather.py   # Main script — all logic in one file
README.md    # This file

Limitations

Temperatures are in Celsius only
Weather codes cover the most common conditions; unusual codes will display as "Weather code N"
Nominatim geocoding requires an internet connection and may be slow on first lookup


Possible Extensions

Add a --units imperial flag for Fahrenheit
Show hourly breakdown instead of daily summary
Wrap in a simple web UI using Flask
Add a 7-day forecast view
