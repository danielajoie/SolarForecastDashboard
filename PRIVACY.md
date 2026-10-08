# Privacy

Solar Forecast Dashboard is a free hobby project by Dan Lajoie. This note explains what data it handles.

## If you don't sign in

Everything stays in your browser. Your settings and readings are saved in your browser's local storage (`solarDash_*` keys) and are never sent to us. The page asks [Open-Meteo](https://open-meteo.com/) for weather at the location you set, and it loads its code libraries from the jsDelivr CDN.

## If you sign in

Sign-in is optional. It uses an email magic link through [Supabase](https://supabase.com/), and the email is delivered by Resend. When you sign in, the following is stored in the project's Supabase database:

- Your email address and an account ID
- Your settings: location (latitude, longitude, ZIP), array details (name, watts, tilt, azimuth, derate), the data-source label, and the name of any CSV you loaded
- Your readings: dates, cumulative kWh, battery-full (CV) flags, and notes
- The time your data was last updated

Database security rules let each signed-in user read and change only their own data.

We don't sell or share your data, and we don't use it for advertising or tracking.

## Deleting your data

Signing out doesn't delete anything from your account. To delete your account, sign in and click **Delete account**. It's in the Cloud sync bar next to **Sign out**, and also under **Settings → Account**. Type `DELETE` to confirm, then click **Delete account permanently**.

That permanently removes the cloud copy of your settings and readings and your sign-in account. If you sign in again later with the same email, you'll start a new, empty account.

Data saved in your browser is kept unless you tick **Also clear data saved in this browser** in the same dialog. That option removes this browser's settings, readings, and cached weather, and resets the dashboard to the example defaults.

## Service limits

This runs on Supabase's free plan. If the project sits unused for about a week it may pause, and sign-in and sync stop working until it's restored. The dashboard keeps working in signed-out mode in the meantime.
