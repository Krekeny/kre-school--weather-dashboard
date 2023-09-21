# KreSchool – Weather Dashboard

##### Example of how this could look. Be **creative**!

![Weather Dashboard](https://cdn.dribbble.com/users/2367559/screenshots/14096604/media/6ebe5a1e5fa9e8fbbe8f48534cd8abde.png)

## Learning Outcomes

> Understand how to fetch data from APIs and handle responses.
> Work with JSON data in JavaScript.
> Dynamically update HTML content using JavaScript.
> Gain practical experience in building a small, complete project.
> By the end of this exercise, you should have a functional weather dashboard where users can view weather information.

---

## 1. Project Setup

Create a new HTML file (e.g., `index.html`), a JavaScript file (e.g., `script.js`), and a CSS file (e.g., `style.css`).

## 2. API Key

Choose a public weather API like `OpenWeatherMap`, `Weatherstack`, **or similar**.

1. Sign up and
2. get an `API key`.

## 3. Basic HTML Structure

Create a basic HTML structure with placeholders for the weather data (e.g., temperature, humidity, weather description).

## 4. Styling

Add some basic styling in your CSS file to make the dashboard look nice.

## 5. Fetch Weather Data

We are using a JavasScript built in function to `fetch` weather data.
You can learn more about the `fetch` function from the [MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch).

Use this function to fetch weather data from the API

Example:

```javascript
const apiKey = "YOUR_API_KEY_HERE";
const city = "New York"; // example city
const url = `http://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}`;

fetch(url)
  .then((response) => response.json())
  .then((data) => {
    console.log(data); // View the returned data to understand its structure
    // Update your HTML with this data
  })
  .catch((error) => console.log("Error:", error));
```

## 6. Display Weather Data

Parse the fetched JSON data and populate the HTML placeholders with the data.

Example:

```javascript
document.getElementById("weather-info").innerHTML = `
    <h2>${data.name}</h2>
    <p>Temperature: ${data.main.temp}</p>
    <p>Humidity: ${data.main.humidity}</p>
    <p>Description: ${data.weather[0].description}</p>
`;
```

## 7. Extra

- Add the ability to search for weather in different cities.
- Display additional information like wind speed, weather icons, etc.
- Implement a loading spinner that shows while data is being fetched.
- Add error handling for scenarios like incorrect city names or network issues.
