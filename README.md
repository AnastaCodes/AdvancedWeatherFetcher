# Advanced Weather Dashboard

**A full weather dashboard — current conditions, 5-day and hourly forecast, air quality and UV index — with a server-side proxy keeping the API keys private.**

**[Live page](https://anastacodes.github.io/AdvancedWeatherFetcher/)** · *Note: the backend proxy was hosted on Adaptable.app, which has since shut down, so the live page currently loads without data. Deploy your own [WeatherProxyServer](https://github.com/AnastaCodes/WeatherProxyServer) instance to bring it back (see below).*

## Features

- **Current weather**: temperature, conditions, humidity, pressure, wind, sunrise/sunset
- **5-day forecast** and **hourly forecast**
- **Air Quality Index**: CO, NO₂, O₃, SO₂, PM2.5, PM10 and more
- **UV index** for the selected location
- **Dark mode** toggle, persisted in `localStorage`
- **Location detection**: browser geolocation with IP-address fallback
- City search

## Architecture

```
Browser (this app) ──▶ WeatherProxyServer (PHP) ──▶ OpenWeatherMap / ipify
```

The frontend never sees the API keys — all requests go through [WeatherProxyServer](https://github.com/AnastaCodes/WeatherProxyServer), a small PHP proxy that holds the keys in server-side environment variables.

## Tech stack

Vanilla HTML / CSS / JavaScript · OpenWeatherMap API · PHP proxy backend

## Run locally

1. Deploy [WeatherProxyServer](https://github.com/AnastaCodes/WeatherProxyServer) (any PHP host works) with your OpenWeatherMap and ipify keys.
2. Point the proxy URL in `app.js` to your instance.
3. Serve this folder, e.g. `npx serve .`

## Acknowledgments

- Weather data by [OpenWeatherMap](https://openweathermap.org/).
