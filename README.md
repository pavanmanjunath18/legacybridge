# LegacyBridge

![status](https://img.shields.io/badge/status-building-orange)

Unified REST API over fragmented legacy systems: one query, one data model, many backends.

**Stack:** TypeScript, Node.js, Fastify, PostgreSQL, Redis, WebSockets, Vitest, React

> **Status: Building.** Launching soon.

## Highlights

- One unified data model and query interface over a SQL database, a REST API, a SOAP service, and CSV export drops
- Adapter per legacy system, with shared filters and cursor pagination
- Redis caching layer with explicit invalidation
- Change polling for systems with no webhooks, with events pushed to clients over WebSockets
- Automatic retry and resume when a WebSocket client disconnects
- Contract-test framework that runs checks per adapter and endpoint, validated against deliberately seeded edge-case bugs
- CI on GitHub Actions
- Small React viewer for browsing unified records and live events

Benchmarks will be published here once measured.

## Layout

```
mocks/      four mock legacy systems (SQL, REST, SOAP, CSV drop) with seeded quirks
src/        Fastify API, unified model, adapters, cache, change feed
viewer/     React viewer
contract/   Vitest contract-test framework and seeded-bug fixtures
bench/      benchmark scripts and results
docs/       design notes, ADAPTERS.md
.github/    CI workflows
```

## Roadmap

- [ ] Phase 1: stack decision and project scaffold
- [ ] Phase 2: mock legacy systems, unified model, adapters
- [ ] Phase 3: caching, change feed, WebSocket delivery
- [ ] Phase 4: contract tests and CI
- [ ] Phase 5: benchmarks and published results
