# Stocker

Stocker is a Next.js 14 app for exploring market data, visualizing stocks with TradingView widgets, and managing personal watchlists.

## Features

- Next.js App Router with server components and suspense-friendly layouts.
- Tailwind CSS design system with custom OKLCH color themes.
- Live TradingView widgets for symbol info, candlestick, baseline, technical analysis, profile, and fundamentals.
- Credential-based authentication backed by Better Auth + MongoDB.
- Watchlist management with optimistic UI and toast feedback.
- Inngest-powered background jobs and email notifications via Nodemailer.

## Tech Stack

- **Frontend:** Next.js 14, React Server Components, Tailwind CSS, Geist font.
- **Data & Services:** Finnhub APIs, TradingView widget embeds, MongoDB via Mongoose.
- **Auth:** Better Auth, JWT sessions, middleware guards.
- **Tooling:** TypeScript, ESLint, Prettier, PostCSS, Turbopack, Sonner toasts.

## Getting Started

```bash
# 1. Install dependencies
npm install

# 2. Copy env template and fill secrets
cp .env.example .env.local

# 3. Run database (e.g. MongoDB Atlas or local mongodb)

# 4. Start dev server
npm run dev
```

Open http://localhost:3000 to view the app.

### Required Environment Variables

Configure at least:

```
NEXT_PUBLIC_FINNHUB_API_KEY=
MONGODB_URI=
BETTER_AUTH_SECRET=
EMAIL_SERVER_HOST=
EMAIL_SERVER_PORT=
EMAIL_SERVER_USER=
EMAIL_SERVER_PASSWORD=
EMAIL_FROM=
```

## Project Structure

```
app/                # App Router layouts & pages
components/         # UI and feature components (TradingView widgets, forms, buttons)
lib/                # Utilities, constants, server actions, external clients
database/           # Mongo connection and Mongoose models
hooks/              # Custom React hooks
middleware/         # Auth and routing middleware
public/             # Static assets (icons, images)
```

## Scripts

```bash
npm run dev      # Start dev server (Turbopack)
npm run build    # Build production bundle
npm run start    # Start production server
npm run lint     # Lint and type-check
```

## Testing & Quality

- ESLint config lives in `eslint.config.mjs`.
- TypeScript strictness enforced via `tsconfig.json`.
- Use `npm run lint` before PRs; add vitest/jest if unit tests are needed.

## Deployment

Deploy to Vercel or any Node.js hosting:

```bash
npm run build
npm run start
```

Ensure environment variables are supplied on your hosting platform, and MongoDB is reachable from the production environment.
