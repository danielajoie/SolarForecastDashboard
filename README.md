# Solar Forecast Dashboard

A free, single-file solar dashboard that **calibrates to your real system**. Log cumulative kWh meter readings and it learns what your panels actually collect—shading, wiring losses, and all—so the 7-day forecast matches reality, not a textbook array.

**Live demo:** [https://danielajoie.github.io/SolarForecastDashboard/](https://danielajoie.github.io/SolarForecastDashboard/)  
(also: [solar_dashboard.html](https://danielajoie.github.io/SolarForecastDashboard/solar_dashboard.html))

No install. No API keys. Your settings and data stay in your browser.

## What it does

- Load cumulative kWh readings (CSV or typed) and see daily production
- Flag capacity-limited (“batteries full”) days so they don’t drag calibration down
- Pull weather from [Open-Meteo](https://open-meteo.com/) (no key)
- Calibrate a per-array physics model on free-collection days
- Forecast the next 7 days of kWh for your configured arrays

## Quick start

1. Open the [live demo](https://danielajoie.github.io/SolarForecastDashboard/), or download `solar_dashboard.html` and open it in a browser.
2. Sample data loads on first visit so charts aren’t empty. Use **Load sample data** or **Load CSV** anytime.
3. Open **Settings** and set your location and array sizes (watts, tilt, facing).
4. Enter your own cumulative meter readings. More free-collection days → tighter calibration.

Weather and charts need a network connection. Everything else works offline once the page is open.

## CSV format

Cumulative totals (not daily deltas). First row is the baseline; later rows derive daily production.

Typical columns: date, cumulative kWh, optional notes / CV flag. See `solar_history_example.csv` for a synthetic sample.

## Privacy

- Readings and settings are stored only in your browser (`localStorage` keys `solarDash_*`).
- Hosting the static files does **not** collect your data.
- The public demo uses a generic location and synthetic sample data.

## License

[MIT](LICENSE) © 2026 Dan Lajoie
