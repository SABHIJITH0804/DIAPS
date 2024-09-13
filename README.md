
# DIAPS
# Disaster Information Aggregation and Prediction Software

This project is a web-based Disaster Aggregation Software that integrates multiple data sources to display weather forecasts, disaster risks, earthquake data, and elevation information for a user-selected location. The project uses APIs to retrieve and display real-time weather and disaster information and visualizes the data on an interactive map.

## Project Structure

- `index.html`: The main page where users can select a location on the map. Upon clicking, the user is redirected to `details.html`, which displays weather and disaster data for the selected location.
- `details.html`: A page that displays weather forecasts, disaster risk prediction, earthquake data, and elevation information for the location selected on the map in `index.html`.
- `index.js`: Contains the JavaScript logic for the main page, initializing the map and handling user interactions.
- `details.js`: Contains the JavaScript logic for the details page, fetching data from various APIs and rendering it on the page.
- `style.css`: Contains all styles for the pages, including layout, colors, and responsive design.
  
## Features

### 1. **Interactive Map (index.html)**
   - Displays a map using the [Leaflet](https://leafletjs.com/) library.
   - Allows users to click on a location to select it.
   - Redirects users to `details.html` with the latitude and longitude of the selected location passed as URL parameters.

### 2. **Weather Forecast (details.html)**
   - Uses the [WeatherAPI](https://www.weatherapi.com/) to fetch weather forecasts for the next 3 days.
   - Displays key weather data like temperature, humidity, wind speed, and rain rate.

### 3. **Disaster Risk Prediction**
   - Calculates risk levels for potential disasters such as floods, heavy rain, landslides, and tsunamis.
   - Displays the disaster risks in text format and a visual graph using [Chart.js](https://www.chartjs.org/).
### Disaster Risk Prediction Graph working

The disaster risk graph is implemented using [Chart.js](https://www.chartjs.org/), showing potential risks for various natural disasters such as floods, heavy rain, landslides, and tsunamis. 

#### Y-Axis Behavior:
- **Default**: When all risks are at their lowest (indicating low risk), the Y-axis is set to a minimum value of 1. This prevents the graph from being completely flat, making it easier to interpret and more visually engaging.
- **Dynamic Adjustment**: If any risk value is higher than 1 (indicating a potential risk), the Y-axis will automatically scale to accommodate the highest risk value, ensuring that the graph adjusts dynamically.
- This allows the graph to reflect risk levels clearly, without being skewed by extremely low values or being too static.

#### 4. **Earthquake Data**
   - Fetches recent earthquake data within a 100 km radius of the selected location using the [USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/).
   - Displays information about recent earthquakes, including location, magnitude, and time of occurrence.
   - If no earthquake data is available within 100 km, displays a message: "No recent earthquakes found within 100 km."

### 5. **Elevation Data**
   - Fetches elevation data using the [Open-Elevation API](https://open-elevation.com/).
   - Displays the elevation of the selected location in meters.

### 6. **Tsunami Risk**
   - If the selected location is near a large water body or ocean, a tsunami risk level is displayed.

## Setup Instructions

### Prerequisites
You will need:
- A working web server (for local development, you can use VSCode's Live Server extension, or simply open the files in a browser).
- API keys for the following services:
  - [WeatherAPI](https://www.weatherapi.com/)
  - [Open-Elevation API](https://open-elevation.com/)
  - [USGS Earthquake API](https://earthquake.usgs.gov/fdsnws/event/1/)

### Installation
1. Clone the repository to your local machine:
   ```bash
   git clone https://github.com/your-username/disaster-aggregation-software.git
