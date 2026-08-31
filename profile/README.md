# SHPE Mobile App

Native mobile application for the **Society of Hispanic Professional Engineers (SHPE)** chapter, built for iOS and Android.

## What it does

- **Scan attendance** at events (primary workflow)
- **Browse events** — calendar, details, location, category
- **Read newsletters** — feed, PDF reader, cover images
- **Account** — member info, attendance history, stats

The app is designed to be fast and simple: open, scan, confirm, leave.

## Tech Stack

| Layer | Technology |
|---|---|
| iOS | Swift, SwiftUI, MVVM |
| Android | Kotlin, Jetpack Compose, MVVM |
| Backend | Supabase (Postgres, Auth, Edge Functions, RLS) |
| File Storage | Cloudflare R2 (newsletters, images) |
| Automation | Java, Appium, GitHub Actions |
| CI/CD | GitHub Actions (build, test, evidence) |

Attendance is **server-authoritative** — the client never decides whether a check-in is valid.

## Repositories

| Repo | Purpose |
|---|---|
| `ios-app` | Native iOS client |
| `android-app` | Native Android client |
| `automation` | Java/Appium test suite + CI |
| `docs` | Architecture, business rules, agent guidelines |

## Architecture

```
iOS / Android (native)
        |
    Supabase (Postgres, Auth, Edge Functions)
        |
    Cloudflare R2 (newsletter files, images)
```

One backend serves both mobile clients today, and can serve a future web client with no changes.

## Status

🚧 Active development — MVP in progress.
