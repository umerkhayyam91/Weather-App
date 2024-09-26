Django Weather App
This is a simple weather detection application built using Django. The app allows users to search for the current weather in any city using the OpenWeatherMap API and displays the weather data including temperature, pressure, humidity, and geographical coordinates.

Features
Search weather by city name.
Display country code, coordinates (longitude and latitude), temperature (in Kelvin), pressure, and humidity.
Uses OpenWeatherMap API to fetch live weather data.
Simple and clean Bootstrap UI.
Installation
1. Clone the repository
bash
Copy code
git clone https://github.com/yourusername/weather-app.git
cd weather-app
2. Create and activate a virtual environment (optional, but recommended)
bash
Copy code
python -m venv venv
source venv/bin/activate  # For Windows: venv\Scripts\activate
3. Install dependencies
Make sure you have Django installed. If not, you can install it via pip:

bash
Copy code
pip install django
4. Get an OpenWeatherMap API Key
Sign up at OpenWeatherMap and get a free API key.
Replace the appid in views.py with your API key:
python
Copy code
res = urllib.request.urlopen("http://api.openweathermap.org/data/2.5/weather?q="+city+"&appid=YOUR_API_KEY").read()
5. Run the development server
bash
Copy code
python manage.py runserver
Open your browser and go to http://localhost:8000.
Usage
On the homepage, enter the name of the city in the search bar.
Submit the form, and the app will display:
Country code
Coordinates (longitude and latitude)
Temperature in Kelvin
Atmospheric pressure (in hPa)
Humidity (in %)
Code Overview
index.html (Template)
This file is responsible for the front-end display of the app:

It uses Bootstrap for styling and includes a search bar for entering the city name.
The results are displayed on the same page, including temperature, pressure, humidity, and more.
views.py (View Logic)
The main logic of the application:

Handles both GET and POST requests.
When a city is entered in the search bar and submitted, it makes a request to the OpenWeatherMap API to fetch the weather data.
The weather information is processed and passed to the template for rendering.
urls.py (Routing)
Ensure that your urls.py file routes the index view properly:

python
Copy code
from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),
]
Future Enhancements
Improve UI/UX for better presentation.
Add more weather details such as wind speed, weather description, etc.
Add error handling for invalid city names.
Add unit conversion (Kelvin to Celsius/Fahrenheit).
Contributing
Contributions are welcome! Please submit a pull request or open an issue for discussion.
