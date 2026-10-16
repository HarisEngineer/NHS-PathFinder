# NHS PathFinder

Step-by-step wayfinding for patients and visitors at Northern General Hospital, Sheffield. Choose where you are and where you need to go, and PathFinder walks you through the route one photo at a time, in your own language, with a step-free option.

Built by a team of five Software Engineering students at Sheffield Hallam University as a Professional Software Projects group project (January–April 2026).

## Features

- **Shortest or step-free routes:** routes are found with Dijkstra's algorithm over a graph of hospital locations, with a step-free alternative that avoids stairs.
- **Photo-guided directions:** each stage of the route shows a photo, so visitors can match the directions to what they see.
- **25 languages:** the interface is translated with next-intl, and route text is translated with the Google Cloud Translation API.
- **Read-aloud directions:** directions can be spoken using the browser's speech synthesis.
- **Accessibility controls:** adjustable text size, high contrast and a more readable font.
- **QR codes at entrances:** scanning an entrance's QR code opens the app with that entrance already set as the starting point.
- **Works offline:** a service worker caches pages, routes and photos so directions still load with a weak signal.
- **Staff admin area:** staff sign in to add locations, connect them into routes and upload route photos.

## Tech stack

Next.js 16 (App Router) · React 19 · TypeScript · Tailwind CSS 4 · Prisma with SQLite · next-intl · Vitest · Vercel

## Run it locally

You need Node.js 20 LTS.

```bash
cd nhs-finder
npm install
npm run dev
```

Then open http://localhost:3000. The demo data is in `nhs-finder/prisma/PathfinderDB.db`.

To run the tests:

```bash
npm test
```

## Project structure

| Folder | What it holds |
| --- | --- |
| `nhs-finder/app` | Pages (home, directions, map, settings, admin) and API routes |
| `nhs-finder/lib/dijkstra.ts` | Route finding, including the step-free option |
| `nhs-finder/components` | Shared UI, including the accessibility toolbar |
| `nhs-finder/messages` | Translation files for the 25 languages |
| `nhs-finder/prisma` | Database schema, migrations and the SQLite demo database |
| `nhs-finder/__tests__` | Database and route-finding tests |
| `Documentation` | User stories, wireframes and the database design |

## How we worked

- Wrote user stories and prioritised them with MoSCoW (Must, Should, Could, Won't have this time) to agree a minimum viable product.
- Worked on feature branches and merged them into `main` through pull requests.
- Reviewed progress as a team at the end of each session, and each member kept an individual work diary.

## Team

Group 2, Sheffield Hallam University. The repository is maintained by [Haris Mahmood](https://www.linkedin.com/in/haris-mahmood-10274a329), who built the multi-language support, read-aloud directions, accessibility controls, staff photo uploads, entrance QR codes and offline caching.
