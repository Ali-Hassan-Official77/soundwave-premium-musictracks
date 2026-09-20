# SoundWave — Production Music Platform

A polished Next.js music discovery and streaming interface powered by the Audius API.

## Stack

- Next.js App Router
- React
- Motion
- Lucide React
- Audius REST API

## Environment

Create `.env.local` from `.env.local.example`:

```env
AUDIUS_API_KEY=your_api_key
AUDIUS_BEARER_TOKEN=your_bearer_token
AUDIUS_API_BASE_URL=https://api.audius.co/v1
```

Keep the Bearer Token server-side. Do not rename it to `NEXT_PUBLIC_*`.

## Run

```bash
npm install
npm run lint
npm run build
npm run dev
```

## Production architecture

- `/api/trending` loads trending Audius tracks.
- `/api/search` searches the Audius catalog.
- `/api/stream/[id]` proxies audio streams and forwards HTTP Range requests for seeking.
- `/api/image` proxies Audius artwork so cards remain same-origin and deployment-safe.
- `public/logo.svg` and `public/favicon.svg` contain the supplied SoundWave mark.
- `public/hero-banner.svg` is the deployment-safe hero artwork built around the supplied mark.

## Frontend features

- Responsive desktop/mobile navigation
- Auto-rotating featured hero
- Continuous trending rail with pause-on-hover
- Search with debounce
- Favorites persisted in localStorage
- Recently played library persisted in localStorage
- Curated playlist views
- Streaming player with play/pause, previous/next, shuffle, repeat, seek and volume
- Deployment-safe local branding assets
