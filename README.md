# EcoSmart - Smart E-Waste Bin System

EcoSmart is a UX-first web & PWA prototype helps users find nearby e-waste bins, deposit items via AI-powered scanning, and get immediate rewards.

## 🚀 Features
- **Smart Finder**: Locate compatible bins with realtime status.
- **AI Detection**: Identify e-waste type and condition using multimodal AI (simulated via Edge Function/API).
- **Gamification**: Earn points, badges, and view environmental impact (CO2 saved).
- **Admin Dashboard**: Optimize collection routes based on bin fill levels.

## 🛠 Tech Stack
- **Frontend**: Next.js 15 (App Router), Tailwind CSS v4, Lucide Icons.
- **Backend**: Next.js API Routes (acting as Edge Functions for demo), Supabase (Database).
- **AI**: OpenRouter (Google Gemini 2.0 Flash) for image analysis.
- **Maps**: Simulated Mapbox/Google Maps integration.

## 📦 Setup & Run

1. **Clone & Install**
   ```bash
   git clone <url>
   cd ios-ewaste-app
   npm install
   ```

2. **Environment Variables**
   Copy `.env.example` to `.env.local` and fill in your keys:
   ```bash
   cp .env.example .env.local
   ```
   *Required Keys*: `NEXT_PUBLIC_SUPABASE_URL`, `NEXT_PUBLIC_SUPABASE_ANON_KEY`, `OPENROUTER_API_KEY`.

3. **Database Setup (Supabase)**
   - Go to Supabase SQL Editor.
   - Run the contents of `supabase/migrations/20240202000000_schema.sql`.
   - Run the contents of `supabase/seed.sql` to populate bins and users.

4. **Run Development Server**
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000).

## 📱 User Flow (Demo)
1. **Landing**: Click "Find Nearest Bin".
2. **Finder**: Select "Phone" type. Tap on a bin marker or list item -> Navigate.
3. **Bin**: Arrive at bin. Tap "Tap to Scan QR" to simulate connection.
4. **Deposit**:
   - Take a photo of an e-waste item (or upload sample).
   - Adjust "Simulated Weight" slider.
   - Click "Analyze Item".
   - View AI result (Type, Confidence, Value).
   - Click "Confirm".
5. **Profile**: View updated points and CO2 stats.

## ⚠️ Notes for Judges
- **Simulations**: Hardware sensors (weight scale) and bin screens are simulated via UI controls.
- **Map**: The map is a visual simulation for the MVP to avoid API key dependencies during review, but designed to drop-in Mapbox GL.
- **AI Fallback**: If no OpenRouter key is provided, the system uses a heuristic fallback (mock) to ensure the demo always works.
