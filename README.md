# Weather App

A React weather app that shows current conditions and a 7-day forecast for any city. The page background is a sky that changes with the weather and the time of day.

**Live demo:** https://salambayo3.github.io/weather-app-react/

![Weather app screenshot](screenshot.png)

## Features

- Search any city and see its current temperature, conditions, feels-like temperature, and wind
- 7-day forecast with a range bar for each day, drawn on one shared scale so days are easy to compare
- Switch between °C and °F (wind switches between km/h and mph)
- Background sky changes for clear, cloudy, rain, storm, snow, and fog, with separate day and night looks
- Remembers your last city and temperature unit
- Clear messages when a city isn't found, the network is down, or the weather service is unavailable
- Cancels outdated requests, so a slow search can't overwrite a newer one
- Responsive layout, keyboard focus styles, and reduced-motion support

## Tech stack

- [React](https://react.dev) with hooks (`useState`, `useEffect`, `useRef`)
- [Vite](https://vite.dev) for development and builds
- [Open-Meteo](https://open-meteo.com) geocoding and forecast APIs (no API key needed)
- Plain CSS with custom properties for the sky themes
- [GitHub Pages](https://pages.github.com) for hosting, deployed with `gh-pages`

## Getting started

You need [Node.js](https://nodejs.org) 20 or newer.

```bash
git clone https://github.com/salambayo3/weather-app-react.git
cd weather-app-react
npm install
npm run dev
```

Open the address printed in the terminal (usually `http://localhost:5173`).

To test the production build locally:

```bash
npm run build
npm run preview
```

## Deploying to GitHub Pages

1. Set `base` in `vite.config.js` to your repo name:

   ```js
   base: "/weather-app-react/",
   ```

2. Deploy:

   ```bash
   npm run deploy
   ```

3. In the repo, go to **Settings → Pages** and set the source to the `gh-pages` branch and the `/ (root)` folder.

## Project structure

```
src/
├── App.jsx     UI, data fetching, and the weather-code lookup
├── App.css     Layout and sky themes
├── index.css   Global reset
└── main.jsx    App entry point
```

## How it works

1. The city name is sent to the Open-Meteo geocoding API, which returns coordinates.
2. The coordinates are sent to the forecast API, which returns current weather and a daily forecast.
3. Temperatures are stored in °C and converted only when displayed, so switching units never needs a new request.
4. Open-Meteo returns numeric weather codes, which the app maps to a label, an icon, and a sky theme.

## Ideas for next steps

- "Use my location" button with the browser's geolocation API
- Hourly forecast for the next 24 hours
- City suggestions while typing

## Credits

- Weather data by [Open-Meteo.com](https://open-meteo.com), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- Font: [Bricolage Grotesque](https://fonts.google.com/specimen/Bricolage+Grotesque) via Google Fonts

Built by [@salambayo3](https://github.com/salambayo3).# weather-app-react
