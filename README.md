# LIGAO RIDE — Frontend + Supabase Starter

A responsive starter app for a Ligao City motorcycle ride and self-drive rental platform. Includes Leaflet + OpenStreetMap, customer email/password authentication, and a first version of online booking persistence using Supabase.

## 1. Configure Supabase
1. Open your Supabase project dashboard.
2. Go to **Project Settings → API** (or **Connect**, depending on the dashboard layout).
3. Copy the **Project URL** and the **anon/public key**. Never use the `service_role` key in frontend code.
4. Open `config.js` and replace:
   - `YOUR_SUPABASE_PROJECT_URL`
   - `YOUR_SUPABASE_ANON_KEY`
5. Save the file.

The anon/public key is intended for browser clients only when Row Level Security (RLS) is enabled and policies are correctly configured. Do not disable RLS to make errors disappear.

## 2. Create the database tables
1. In Supabase, open **SQL Editor**.
2. Create a new query.
3. Copy the contents of `supabase_schema.sql` into the editor and run it.
4. Check **Table Editor** for `profiles` and `bookings`.

The SQL sets up profile creation on signup, booking storage, and initial RLS policies. Customers can only read their own bookings and create bookings linked to their own authenticated account.

## 3. Run the website
1. Extract all files from the ZIP into one folder.
2. Open `index.html`, or preferably serve the folder using a local web server.
3. Test via HTTPS or localhost for browser GPS.
4. Click the avatar at the top right to create an account or sign in.
5. Sign in, submit a Pasundo or MotoRent request, then open **My bookings** to check saved requests.

## Included in this starter
- Responsive LIGAO RIDE interface
- Leaflet interactive destination map with OpenStreetMap tiles
- Place lookup using public Nominatim on search submit (not keystroke autocomplete)
- Current location via browser GPS and best-effort reverse geocoding
- Supabase email/password sign-up and sign-in
- Auto-created customer profile row from auth metadata
- Online storage of Pasundo and MotoRent booking requests
- Customer booking history loaded from Supabase
- RLS policies to isolate customer bookings
- `supabase_schema.sql` for the first database schema

## Current limitations — important
This is still a starter prototype, not a production ride-hailing or rental service:
- Driver matching, driver accounts, partner inventory, admin approval, live trip tracking, fare calculation, cancellation management, push notifications, and real payments are not implemented.
- Cash and QR Ph are recorded as a selected preference only; no money is collected or transferred.
- The rental flow stores a request and selected demo motorcycle name; it does not guarantee availability.
- The starter currently supports email/password customer authentication. Phone OTP, password reset UI, email templates, and production account recovery need follow-up work.
- Do not collect real ID photos or sensitive documents through this prototype.
- Keep the Supabase project in RLS mode. Never expose a `service_role` key in `config.js` or any frontend file.

## Maps and free-tier considerations
No Google Maps API key is required. Leaflet is the map library and OpenStreetMap provides tiles. Public OpenStreetMap tile and Nominatim services have usage policies, capacity limits, and no uptime guarantee. Keep attribution visible, avoid automated/bulk lookups, and review current usage policies before launch. A growing production service should use a suitable hosted provider or its own geocoding/tile infrastructure.

Before a real launch, check applicable transport/rental permits, insurance, contracts, privacy and data-protection obligations, driver/renter verification, and safety procedures.
