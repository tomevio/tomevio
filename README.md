<div align="center">
  <h1>Tomevio</h1>
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="assets/logo-light.svg">
    <img alt="Tomevio: Your personal book tracking companion"
         src="assets/logo-light.svg"
         width="50%">
  </picture>
  <p>Track and discover books across devices. The FOSS way.</p>
</div>

## Overview

**Tomevio** is a full-stack, open-source book tracking platform. It brings together:

- A **Next.js-powered website**
- A **high-performance Rust backend**
- A **Flutter-based mobile app**

This monorepo ties together all components under one roof using Git submodules. Whether you're searching for books, exploring authors, or managing your personal collection—Tomevio offers a fast, clean, and consistent experience on any device.

## Monorepo Structure

```

tomevio/
├── website/       # Web frontend (Next.js + TypeScript)
├── backend/       # REST API (Rust + Axum)
└── mobile-app/    # Cross-platform mobile app (Flutter)

````

Each folder links to a separate GitHub repo and includes its own README and instructions.

## Quick Start

### Clone the Monorepo (with submodules)

```bash
git clone --recurse-submodules https://github.com/s4nj1th/tomevio.git
cd tomevio
````

If you already cloned without submodules:

```bash
git submodule update --init --recursive
```

Then follow each component’s README to get it running locally.

## Project Highlights

### Website ([tomevio-website](https://github.com/s4nj1th/tomevio-website))

* Built with **Next.js**, **TypeScript**, and **API integration**
* Features real-time book search, author pages, and responsive layout
* Optimized for performance using static generation and modern frontend practices

### Backend ([tomevio-backend](https://github.com/s4nj1th/tomevio-backend))

* Written in **Rust**, using **Axum**, **Tokio**, and **Reqwest**
* Integrates with the OpenLibrary API for metadata
* Clean modular structure with fast, scalable REST API endpoints

### Mobile App ([tomevio-mobile-app](https://github.com/s4nj1th/tomevio-mobile-app))

* Developed in **Flutter**, supports **Android & iOS**
* Features search, book info, author pages, and future syncing
* Mobile-optimized layout and smooth native performance

## Local Setup Summary

| Component     | Stack/Tools      | Commands                         |
| ------------- | ---------------- | -------------------------------- |
| `website/`    | Node.js, Next.js | `npm install && npm run dev`     |
| `backend/`    | Rust, Cargo      | `cargo build && cargo run`       |
| `mobile-app/` | Flutter SDK      | `flutter pub get && flutter run` |

**Configuration files** like `.env.local` (for web) and `constants.dart` (for mobile) must be updated with the correct API base URL.

## Environment Configs

Each component expects the backend API to be running locally at:

```
http://localhost:8080
```

You can override this as needed:

* Web: `.env.local → NEXT_PUBLIC_API_BASE_URL`
* Mobile: `lib/constants.dart → apiBaseUrl`

## Project Architecture

### Shared Features Across Platforms

* Book/author search powered by OpenLibrary
* Book details with cover, summary, publish info
* Author bios and bibliographies
* Sync-ready backend
* High performance and responsiveness

## Contributing

Contributions are welcome to any module!

Please follow best practices for each tech stack:

* **Web**: Prettier formatting, modular React components
* **Backend**: `cargo fmt`, idiomatic Rust code
* **Mobile**: `flutter format`, clean separation of concerns

Open a pull request in the relevant submodule repo. Feature ideas, bug reports, and docs improvements are appreciated.

## License

All Tomevio repositories are open-sourced under the [MIT License](LICENSE).

## Maintainer

**Sanjith** -
[GitHub](https://github.com/s4nj1th) · [Twitter/X](https://x.com/s4nj1th) · [Email](mailto:sanjith.develops@gmail.com)

## Roadmap (Planned)

- Reading lists and bookshelf views
- User authentication + account syncing
- Offline support for mobile
- Deployable Docker configs / CI workflows

## Related Repos

| Name       | Description                 | Link                                                                |
| ---------- | --------------------------- | ------------------------------------------------------------------- |
| Website    | Next.js frontend            | [tomevio-website](https://github.com/s4nj1th/tomevio-website)       |
| Backend    | Rust API server             | [tomevio-backend](https://github.com/s4nj1th/tomevio-backend)       |
| Mobile App | Flutter app for Android/iOS | [tomevio-mobile-app](https://github.com/s4nj1th/tomevio-mobile-app) |

> Tomevio is an ongoing passion project. If you're interested in contributing, collaborating, or building on top of it—reach out or fork and start exploring.
