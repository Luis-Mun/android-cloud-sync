# Android Cloud Sync

> **Status: planned. Not started yet.** This repository currently contains the project scaffold and roadmap only.

Offline-first Android app that syncs a local Room database with a secure REST API backed by AWS RDS PostgreSQL.

## Overview

Builds on the [android-mvvm-refactor](../android-mvvm-refactor) app. Local Room data stays as an offline cache; a Node/Express API with PostgreSQL is the system of record. Users register and log in, create data offline, and changes sync in the background with conflict handling.

## Skills demonstrated

Android, Retrofit, WorkManager, Node.js/Express, PostgreSQL, AWS RDS, JWT auth, API security

## Planned structure

```
android-cloud-sync/
├── android/          # MVVM app + Retrofit + WorkManager sync
├── backend/          # Express API (routes, controllers, middleware, models)
├── database/schema.sql
└── docs/             # API + security documentation
```

## Roadmap

- [ ] Document current Room schema; add per-user ownership and sync metadata (`updated_at`, tombstones)
- [ ] PostgreSQL schema
- [ ] Express API: register, login, `/users/me`, CRUD `/data`
- [ ] Security: HTTPS, bcrypt/Argon2id, short-lived tokens, authorization checks, input validation, parameterized queries, rate limiting, secrets management
- [ ] AWS: private RDS PostgreSQL + API deployment
- [ ] Android: Retrofit client, login/register, CRUD against the API
- [ ] Sync engine with WorkManager: push pending changes, pull remote updates, conflict resolution, last-sync tracking, offline handling
- [ ] End-to-end tests including cross-user access checks
- [ ] API and security documentation

## Getting started

Setup, run, and test instructions will be added as each roadmap item is completed.

## Screenshots

Will be added to `screenshots/` once there is something to show.

## Future improvements

To be added after the first working version.

---

*Needed to proceed:* The finished android-mvvm-refactor app; an AWS account (RDS has a free tier) for the deployment phase. Backend and sync logic can be built and tested locally first..
