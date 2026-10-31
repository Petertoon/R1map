# Restaurant Map (Render / Express)

Same pattern as the property map: Express serves public/index.html (Mapbox) and /api/restaurants,
which reads a Wix CMS collection through the Wix Data API.

## Files
- config/sites.json: one entry per Wix site (domain, env-var names, collection ID, field keys)
- routes/restaurants.js: queries the collection, cleans photos/links/phone, caches 5 minutes
- routes/debug-collections.js: TEMPORARY. /api/debug-collections lists real collection IDs and field keys
- public/index.html: map, pins, bottom card strip with 4 buttons

## Deploy
New GitHub repo, then Render Web Service (build `npm install`, start `npm start`).
Env vars: WIX_API_KEY_R1, WIX_ACCOUNT_ID_R1, WIX_SITE_ID_R1

## Collection fields (or edit the "fields" block in sites.json to match yours)
title, lat, lng, address, phone, menuUrl, pickupMenuUrl, foodPhotos (media gallery), status (optional), cuisine (optional)
