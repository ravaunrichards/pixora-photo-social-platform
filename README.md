# Pixora — Photo and Video Social Platform

Pixora is an independent, responsive photo-sharing social network starter. It is inspired by common photo-social product patterns, but uses original branding and is not affiliated with Instagram or Meta.

## Included
- Responsive desktop/mobile feed and profile layout
- Account registration and sign-in with salted scrypt password hashes
- Signed expiring bearer tokens
- Photo and short-video posts (JPG, PNG, WebP, GIF, MP4, WebM), captions and local media storage
- For-you and following feeds
- Likes, comments, user search and follow/unfollow
- Profile display name and bio editing
- Local JSON persistence and API
- Automated API smoke test using Node's built-in test runner

## Requirements
Node.js 20 or newer. No external npm packages are required.

## Run
```bash
npm test
npm start
```
Open http://localhost:3000.

## Configuration
Copy `.env.example` to `.env` if your deployment environment loads it, then configure `PORT`, `SESSION_SECRET`, and `MAX_UPLOAD_BYTES` in the environment. The built-in server does not automatically parse `.env`; export variables in your shell or use a deployment platform's environment settings. Replace the development secret before exposing this application to the internet.

## API overview
- `GET /api/health`
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/me` and `PATCH /api/me`
- `GET /api/users?q=...`
- `GET /api/posts?feed=all|following`
- `POST /api/posts`
- `POST /api/posts/:id/like`
- `POST /api/posts/:id/comments`
- `POST /api/users/:id/follow`

For creating a post, send JSON with `media` set to a base64 data URL and `caption` set to a string. Uploads default to 8 MB.

## Important limitations
This is a starter project, not a production-scale Instagram replacement. It does not yet include stories that expire, direct messages, livestreams, push notifications, image/video transcoding, CDN/object storage, advanced ranking, reporting/moderation, account recovery, or end-to-end security operations. JSON-file storage is intended for local development only. Before public launch, add a production database, object storage, rate limiting, CSRF/origin controls as appropriate, robust input validation, malware scanning, moderation and privacy/legal review. Run tests in your own environment before deployment.

## Project independence
This repository is standalone and does not alter any other project or deployment.
