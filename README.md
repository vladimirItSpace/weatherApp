# Weather Web App


The Weather Web App is a simple Vue.js application that allows users to check the weather information for a specific city. By entering the name of a city, users can quickly retrieve the current weather conditions, including temperature, in Celsius.

## Features

- Input field for users to enter the city name they want to check the weather for.
- Clickable "Insert" button to initiate the weather data retrieval.
- Real-time validation to ensure the city name is at least two characters long before making the API call.
- Display of the city name and corresponding weather temperature in Celsius.

## How to Use

1. Enter the name of the city you want to check the weather for in the input field.
2. Click the "Insert" button to fetch the weather information.
3. The weather details, including the temperature in Celsius, will be displayed below the input field.

## Setup Instructions

To set up the Weather Web App locally on your machine, follow these steps:

1. Clone this repository to your local machine using `git clone`.
2. Navigate to the project directory.
3. Install the required dependencies using `npm install`.
4. Obtain an API key from OpenWeatherMap (sign up for free if you don't have one).
5. Replace the placeholder `appid` in the `axios.get` method inside the script with your actual OpenWeatherMap API key.
6. Run the app locally using `npm run serve`.


## Technologies Used

- Vue.js: A progressive JavaScript framework for building user interfaces.
- Axios: A popular HTTP client library used for making API requests.

## Live Demo

Check out the live demo of the Weather Web App [here](https://your-weather-app-demo.com).


## Contributions

Contributions to the Weather Web App are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## Author

The Weather Web App is developed and maintained by Miron Vladimir

---
