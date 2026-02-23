# Project Overview: immich

## Purpose
High-performance, self-hosted photo and video management solution. A Google Photos alternative with mobile auto-backup, face recognition, AI-powered search, and more. Licensed under AGPLv3.

## Tech Stack
- **Monorepo** managed with pnpm workspaces (v2.5.1)
- **Server**: NestJS (Node.js/TypeScript), TypeORM, PostgreSQL
- **Web**: SvelteKit with Vite, Svelte, TypeScript
- **Mobile**: Flutter/Dart (iOS and Android)
- **Machine Learning**: Python (face recognition, CLIP search, etc.)
- **Infrastructure**: Docker Compose for dev/prod/e2e
- **API**: OpenAPI spec with auto-generated TypeScript and Dart SDKs
- **Testing**: Vitest (server + web), E2E tests with Docker Compose
- **i18n**: Internationalized with 18+ languages

## Key Files
- `server/` — NestJS backend (API, database migrations, media processing)
- `web/` — SvelteKit frontend (web UI)
- `mobile/` — Flutter mobile app (iOS/Android)
- `machine-learning/` — Python ML microservice (face detection, CLIP, etc.)
- `cli/` — Command-line interface tool
- `open-api/` — OpenAPI spec and SDK generation scripts
- `docker/` — Docker Compose files (dev, prod) and example env
- `e2e/` — End-to-end test suite
- `docs/` — Documentation site
- `Makefile` — Top-level dev/prod/e2e orchestration commands
- `pnpm-workspace.yaml` — Monorepo workspace definition
- `i18n/` — Internationalization files

## Build/Run Commands
- `make dev` — Start full dev environment via Docker Compose
- `make dev-update` — Rebuild and start dev environment
- `make prod` — Start production environment
- `make e2e` — Run end-to-end tests
- `make open-api` — Regenerate OpenAPI SDKs
- `pnpm install` — Install Node.js dependencies
- Server: `npm run start:dev` (inside server/)
- Web: `pnpm run dev` (inside web/, port 3000)
- ML: Python-based with pyproject.toml (uv.lock for dependencies)

## Notes
- Very large, mature open-source project with active community
- Multi-service architecture: server, web, mobile, ML, all orchestrated via Docker
- Hardware acceleration support for transcoding and ML inference (hwaccel configs)
- Uses Renovate for dependency updates
- Has CODEOWNERS, CODE_OF_CONDUCT, CONTRIBUTING, SECURITY docs
- Mobile uses Flutter with Drift for local DB, Pigeon for platform channels
- OpenAPI-first approach: API spec drives SDK generation for both TypeScript and Dart
- Plugins system exists (`plugins/` directory)
