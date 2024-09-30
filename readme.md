# Weather App

## Functionality Overview:

- **User Interface (UI)**: The user can enter the name of a city and submit the form.
- **Weather Data Fetching**: The app fetches the weather data for the input city using an external weather API.
- **Display Weather**: The app displays relevant weather information (like temperature, conditions, etc.) on the page.
- **Error Handling**: If the city is not found or an error occurs, the app shows an error message.

## Class Outlines:

### WeatherService

- **Purpose**: Handles all API interactions.
- **Responsibilities**:
  - Fetch weather data from the external API based on the city name.
  - Handle possible fetch errors (like invalid city names or network issues).
- **Key Methods**:
  - `getWeather(cityName)` - This will make the fetch request and return the weather data.

### UIHandler

- **Purpose**: Manages DOM updates (displaying results and handling user input).
- **Responsibilities**:
  - Get the input (city name) from the user.
  - Update the DOM with weather data or an error message.
- **Key Methods**:
  - `showWeather(data)` - Takes weather data and displays it.
  - `showError(message)` - Displays error messages to the user.
  - `clearInput()` - Clears the input field after submission.

### AppController

- **Purpose**: Orchestrates interactions between `WeatherService` and `UIHandler`.
- **Responsibilities**:
  - Capture the user's city input.
  - Call `WeatherService` to fetch data.
  - Use `UIHandler` to display the fetched data or show errors.
- **Key Methods**:
  - `handleSearch()` - Called when the user submits the form. It will fetch the data and update the UI accordingly.

## Flow of the App:

1. **User Action**: User enters a city and submits the form.
2. **AppController**: `handleSearch()` is triggered, fetches data via `WeatherService`.
3. **WeatherService**: Fetches weather data from API and returns it.
4. **UIHandler**: Displays data (or an error) based on the response.
