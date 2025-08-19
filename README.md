## AI Powered Waste Recognition and Management Application

<img width="1903" height="992" alt="Home" src="https://github.com/user-attachments/assets/5ee5fe92-6501-4f48-9de3-d7a1a4dc21e7" />

ECOZEN is a Next.js application that helps communities report and collect waste, verify submissions with AI, and reward contributions with points. Users can:

- Report waste with photo verification
- Pick up/verify reported waste and earn points
- Redeem rewards and view transaction history
- Compete on a leaderboard

### Tech Stack
- Next.js (App Router) + React 19
- Tailwind CSS + shadcn/ui + lucide-react
- Firebase Authentication (Google Sign-In)
- Postgres (Neon) + Drizzle ORM
- Google Maps Places API
- Google Gemini API (client-side verification)

---

## Getting Started

### Prerequisites
- Node.js 18+ and npm
- A Postgres database (Neon recommended)
- A Firebase project with Google sign-in enabled
- Google Maps API key (Places)
- Gemini API key

### 1) Install dependencies
```bash
npm install
```

### 2) Environment variables
Create a `.env` file in the project root with the following variables (fill in your values):
```bash
# Firebase (client-side)
NEXT_PUBLIC_FIREBASE_API_KEY=...
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=...
NEXT_PUBLIC_FIREBASE_PROJECT_ID=...
NEXT_PUBLIC_FIREBASE_STORAGE_BUCKET=...
NEXT_PUBLIC_FIREBASE_MESSAGING_SENDER_ID=...
NEXT_PUBLIC_FIREBASE_APP_ID=...
NEXT_PUBLIC_FIREBASE_MEASUREMENT_ID=...

# Google
NEXT_PUBLIC_GOOGLE_MAPS_API_KEY=...
NEXT_PUBLIC_GEMINI_API_KEY=...

# Database (server-only)
DATABASE_URL=postgres://...
```

Notes:
- Client-side code can only access variables prefixed with `NEXT_PUBLIC_`.
- Keep `DATABASE_URL` private (server-only).

### 3) Database setup (Drizzle + Neon)
- Ensure `DATABASE_URL` points to your Postgres instance.
- Push schema to the database:
```bash
npm run db:push
```
- Optional: open Drizzle Studio
```bash
npm run db:studio
```

### 4) Run the dev server
```bash
npm run dev
```
Visit `http://localhost:3000`.

---

## Features Overview

- Report Waste (`/report`)
  - Upload a photo, AI (Gemini) verifies waste type/quantity
  - Choose location via Google Places autocomplete
  - Submitting a report grants points

- Collect Waste (`/collect`)
  - See nearby tasks (from reports)
  - Claim and verify with a photo; upon verification, earn points

- Rewards (`/rewards`)
  - View current balance and transactions
  - Redeem points or specific rewards

- Leaderboard (`/leaderboard`)
  - Rankings by points

---

## Scripts
```bash
npm run dev         # Start dev server (Next.js)
npm run build       # Production build
npm run start       # Start production server
npm run lint        # Lint
npm run db:push     # Apply Drizzle schema to DB
npm run db:studio   # Open Drizzle Studio
```

---

## Configuration Notes
- Firebase setup steps are summarized in `FIREBASE_SETUP.md`.
- Do not expose `DATABASE_URL` to the client; keep database access on the server.
- Restart the dev server whenever you change env variables.

---

## Deployment
Deploy easily on Vercel:
1. Push this repo to GitHub.
2. Create a Vercel project and import the repo.
3. Add all required environment variables in Vercel Project Settings.
4. Connect your Neon database URL to `DATABASE_URL`.

---

## License
This project is licensed under the MIT License.

