# Live Quiz Scoreboard

Real-time quiz competitions: a host screen, contestants on their phones, live scoring and a lag indicator per player.

> **Status: in development.** This repo is the plan and the write-up; the interactive demo is being built next.
> Star or watch the repo to see it land. The live demo link will appear here.

Part of [Julynard Tago-on's portfolio](https://julynardtago-on.netlify.app/#projects). Based on the science quiz bee system I built for a national statistics agency.
Client code is private, so this is a clean-room demo with fictional data. No client names or real data.

## What the demo will show

- [ ] The host screen shows a room code and QR; contestants join from their phones
- [ ] The host starts a question, answers lock at the deadline, and the scoreboard updates live
- [ ] A **lag indicator** per player (round-trip ping)
- [ ] A multi-tab mode that works without any backend (`BroadcastChannel`), plus Supabase Realtime for real devices

Every key action will have an **"In production"** note explaining how the real system does it.

## How the production system works

The real system runs on Laravel. The demo simulates these behaviours in the browser so it can stay fast and always on.

- Laravel with websockets broadcasting question, lock and score events
- Server-side answer locking so late answers are rejected regardless of client clocks
- Lag measured per contestant so the host can see who is on a bad connection

## Planned stack

- Vue 3 + TypeScript + Vite
- Tailwind CSS v4
- Pinia (state saved in the browser, with a **Reset demo** button)
- Vitest for the domain logic, ESLint + Prettier + `vue-tsc` in CI
- Supabase Realtime broadcast channels (free tier)
- GitHub Actions → GitHub Pages (free, always on)

## Roadmap

1. Project scaffold, CI (lint, type-check, test, build) and GitHub Pages deploy
2. Domain logic with Vitest tests
3. UI with seeded data, guided steps and "In production" notes
4. Screenshot/GIF in this README and the live demo link

## Author

**Julynard Tago-on**, Laravel / PHP full-stack engineer · [Portfolio](https://julynardtago-on.netlify.app) · [GitHub](https://github.com/Julynard) · [LinkedIn](https://www.linkedin.com/in/julynard-tago-on/)

## License

[MIT](LICENSE)
