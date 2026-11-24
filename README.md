# brothers ai — Secure Video Backend

Server-side proxy and video-provider integration layer for the **brothers ai** Android application.
All provider API keys (`GEMINI_API_KEY`, `RUNWAY_API_KEY`, `LUMA_API_KEY`) stay strictly on this server and are **never** embedded in the Android APK.

## Setup

```bash
cd backend
cp .env.example .env
# Add one or more provider API keys in .env
npm install
npm run dev
```

## Endpoints

- `GET /api/v1/health` — Returns backend status and configured provider info
- `POST /api/v1/videos/generate` — Submits a Text-to-Video or Image-to-Video job
- `GET /api/v1/videos/jobs/:jobId` — Polls generation progress and status
- `GET /api/v1/videos/jobs/:jobId/download` — Streams the completed MP4 securely
