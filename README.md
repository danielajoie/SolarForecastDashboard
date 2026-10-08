# Solar Forecast Dashboard

A free, single-file solar dashboard that **calibrates to your real system**. Log cumulative kWh meter readings and it learns what your panels actually collect—shading, wiring losses, and all—so the 7-day forecast matches reality, not a textbook array.

**Live demo:** [https://danielajoie.github.io/SolarForecastDashboard/](https://danielajoie.github.io/SolarForecastDashboard/)  
(also: [solar_dashboard.html](https://danielajoie.github.io/SolarForecastDashboard/solar_dashboard.html))

No install, no API keys, and no account needed. Sign in only if you want your settings and readings saved to your account so they follow you across browsers and devices.

## What it does

- Load cumulative kWh readings (CSV or typed) and see daily production
- Flag capacity-limited (“batteries full”) days so they don’t drag calibration down
- Pull weather from [Open-Meteo](https://open-meteo.com/) (no key)
- Calibrate a per-array physics model on free-collection days
- Forecast the next 7 days of kWh for your configured arrays
- Optional: sign in with an email link to sync your settings and readings across devices

## Quick start

1. Open the [live demo](https://danielajoie.github.io/SolarForecastDashboard/), or download `solar_dashboard.html` and open it in a browser.
2. Sample data loads on first visit so charts aren’t empty. Use **Load sample data** or **Load CSV** anytime.
3. Open **Settings** and set your location and array sizes (watts, tilt, facing).
4. Enter your own cumulative meter readings. More free-collection days → tighter calibration.

Weather and charts need a network connection. Everything else works offline once the page is open.

## Optional sign-in and sync

Use the account bar at the top of the dashboard to sign in with an email magic link (sent from `no-reply@auth.danielajoie.com`). No password.

- On your first sign-in, choose **Upload local data** to keep what's already in this browser, or **Start fresh**.
- While you're signed in, your saved account copy is the one the dashboard uses.
- Signing out switches back to the data stored in this browser.
- Links expire after 1 hour, and you can request one link per minute.
- To remove everything, click **Delete account** (next to **Sign out**, or in **Settings → Account**).

If you never sign in, the dashboard works exactly as before and nothing leaves your browser.

## CSV format

Cumulative totals (not daily deltas). First row is the baseline; later rows derive daily production.

Typical columns: date, cumulative kWh, optional notes / CV flag. See `solar_history_example.csv` for a synthetic sample.

## Privacy

- **Not signed in:** settings and readings stay only in your browser (`localStorage` keys `solarDash_*`). Nothing is sent anywhere except weather requests to Open-Meteo for your location.
- **Signed in:** your email, settings, and readings are stored in the project's Supabase database, and each user can only read their own data.
- The public demo uses a generic location and synthetic sample data.

Details are in [PRIVACY.md](PRIVACY.md).

## License

[MIT](LICENSE) © 2026 Dan Lajoie
