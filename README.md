# LIGAO RIDE — Standalone Frontend Prototype

A responsive starter app for a Ligao City motorcycle ride and self-drive rental platform.

## Run it
1. Extract `ligao_ride_starter.zip`.
2. Open `index.html` in a modern browser, or serve the folder using a static web server.
3. For browser GPS, use HTTPS or `localhost`; browsers generally block geolocation on ordinary `file://` pages.

## Included
- Responsive desktop sidebar and mobile navigation
- Pasundo booking request preview
- MotoRent searchable demo listings and rental request preview
- Booking list, wallet/earnings placeholder, profile and partner application preview
- Local suggestions for common Ligao / nearby places
- Search-on-Enter place lookup using OpenStreetMap Nominatim
- Interactive destination map with draggable pin using Leaflet + OpenStreetMap
- Browser current-location button and best-effort reverse geocoding
- Cash or QR Ph payment selection (demo only)
- Optional rider tip presets and custom tip (demo only)
- Yellow / charcoal / white design

## Map costs and service limits
This version does not require a Google Maps API key or Google Cloud billing setup. Leaflet is the map library; map tiles are served by OpenStreetMap. Place lookup uses the public Nominatim service only when the user submits a search (presses Enter) or selects a map point. It is not designed for keystroke-by-keystroke autocomplete or high-volume production traffic.

OpenStreetMap's public tile and Nominatim services have usage policies and capacity limits. Keep attribution visible, avoid bulk or automated requests, and review the providers' current usage policies before launching. For a growing production app, choose a suitable hosted tile/geocoding provider or operate your own service. Do not assume public services are unlimited or guaranteed uptime.

## Important prototype limitations
This is a frontend prototype only. It does not yet have real user authentication, secure ID upload/verification, a database, live driver dispatch, continuous GPS tracking, real payments, or production booking functionality. Cash/QR Ph selections and rider tips are UI previews only until a payment provider and server-side tip ledger are implemented. Do not collect real identity documents in this demo.

Before operating live passenger transport or rentals, verify applicable permits, insurance, contracts, privacy and safety requirements. Test location accuracy and the user experience on mobile devices before any public launch.
