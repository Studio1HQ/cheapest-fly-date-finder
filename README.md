<div align="center">

<img src="https://raw.githubusercontent.com/Studio1HQ/Studio1HQ/main/assets/banners/cheapest-fly-date-finder.webp" alt="Cheapest Day to Fly Finder: Find the cheapest departure date for a fixed-length trip" width="100%" />

<br />
<br />

# Cheapest Day to Fly Finder

### Find the cheapest departure date for a fixed-length trip

A Next.js app for flexible travelers. Set a departure window and trip length, and it queries Google Flights calendar data through SearchApi and ranks the cheapest round trips.

<br />

[![Built by Studio1](https://img.shields.io/badge/Built_by_Studio1-f97316?style=for-the-badge&logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAxNjAgMTYwIiBmaWxsPSJub25lIj48cGF0aCBmaWxsLXJ1bGU9ImV2ZW5vZGQiIGNsaXAtcnVsZT0iZXZlbm9kZCIgZD0iTTAgMzVDMCAxNi42ODA3IDE0LjA3NDQgMS42NDg0NCAzMiAwLjEyNjk1M1YxNDFINTEuMDUyM0M1Mi40MzA4IDEzNy4zNDQgNTQuNzQ0NiAxMzMuNjg5IDU3Ljk5MzggMTMwLjAzM0M2MS4xNDQ2IDEyNi41MDggNjQuNjg5MiAxMjMuNDQgNjguNjI3NyAxMjAuODI5QzcyLjU2NjIgMTE4LjM0OSA3Ni4zNTY5IDExNi43ODIgODAgMTE2LjEyOVY4Ni43NTQ0Qzc1LjQ3MDggODcuOTI5MiA3MS4zODQ2IDg5LjY5MTkgNjcuNzQxNSA5Mi4wNDE1QzY0IDk0LjUyMjUgNjAuNzUwOCA5Ny40NiA1Ny45OTM4IDEwMC44NTRDNTYuNTM0NSAxMDIuNzIgNTUuMjU0NSAxMDQuNjU5IDU0LjE1MzkgMTA2LjY3MVYwSDEyNUMxNDQuMzMgMCAxNjAgMTUuNjY5OSAxNjAgMzVWMTI1QzE2MCAxNDQuMzMgMTQ0LjMzIDE2MCAxMjUgMTYwSDEyNFYxOEgxMDQuOTQ4QzEwMy41NjkgMjEuNjgxNiAxMDEuMjU1IDI1LjM2MjggOTguMDA2MiAyOS4wNDQ0Qzk0Ljg1NTQgMzIuNTk0MiA5MS4zMTA4IDM1LjY4NDEgODcuMzcyMyAzOC4zMTRDODMuNDMzOCA0MC44MTIgNzkuNjQzMSA0Mi4zODk2IDc2IDQzLjA0NzRWNzIuNjMwNEM4MC41MjkyIDcxLjQ0NzMgODQuNjE1NCA2OS42NzI0IDg4LjI1ODUgNjcuMzA1N0M5MiA2NC44MDc2IDk1LjI0OTIgNjEuODQ5MSA5OC4wMDYyIDU4LjQzMDdDOTkuNDY1NSA1Ni41NTEzIDEwMC43NDUgNTQuNTk4NiAxMDEuODQ2IDUyLjU3MjNWMTYwSDM1QzE1LjY3IDE2MCAwIDE0NC4zMyAwIDEyNVYzNVoiIGZpbGw9IiNmZmZmZmYiLz48L3N2Zz4K)](https://studio1hq.com)
[![Built with SearchApi](https://img.shields.io/badge/Built_with_SearchApi-141414?style=for-the-badge)](https://www.searchapi.io)
[![Live demo](https://img.shields.io/badge/Live_demo-1c1917?style=for-the-badge&logo=vercel&logoColor=white)](https://cheapest-fly-date-finder.vercel.app)

[SearchApi docs](https://www.searchapi.io/docs) &nbsp;·&nbsp; [SearchApi](https://www.searchapi.io) &nbsp;·&nbsp; [More examples](https://github.com/Studio1HQ) &nbsp;·&nbsp; [studio1hq.com](https://studio1hq.com)

</div>

<br />

## Overview

A web app for flexible travelers. Instead of guessing return dates, you give a flexible departure window and a fixed trip length, for example "7 days, leaving any time between Nov 1 and Nov 20". The app queries Google Flights calendar data through [SearchApi](https://www.searchapi.io/?utm_source=Dev&utm_medium=Ambassador&utm_campaign=studio1hq.com), keeps only combinations with the exact duration, ranks them by price and links each result to Google Flights.

It shows how to wrap a search API in Next.js route handlers so the API key stays on the server.

## Features

- **Flexible search**: earliest and latest departure dates plus length of stay in days.
- **Place autocomplete**: debounced city and airport suggestions with IATA codes.
- **Ranked results**: cheapest round trips first, with dates, price and an "Inspect on Google Flights" link.
- **Loading and error states**: skeleton rows, empty state and error state.
- **Server-side key**: the SearchApi key is read only inside route handlers and never reaches the browser.
- **Safe date math**: UTC-based date arithmetic avoids daylight saving and timezone off-by-one errors.

## Tech stack

| Layer | Tool |
| --- | --- |
| Framework | [Next.js](https://nextjs.org) (App Router) |
| Flight data | [SearchApi](https://www.searchapi.io/?utm_source=Dev&utm_medium=Ambassador&utm_campaign=studio1hq.com) Google Flights APIs |
| Styling | [Tailwind CSS](https://tailwindcss.com) v4 |
| Language | TypeScript |
| Deployment | [Vercel](https://vercel.com) |

## Getting started

### Prerequisites

- Node.js 18.17 or later
- npm, pnpm or yarn
- A [SearchApi](https://www.searchapi.io/?utm_source=Dev&utm_medium=Ambassador&utm_campaign=studio1hq.com) API key

### Installation

```bash
git clone https://github.com/Studio1HQ/cheapest-fly-date-finder.git
cd cheapest-fly-date-finder/frontend
npm install
```

### Environment variables

Create `frontend/.env.local` (or `.env`).

| Variable | Description |
| --- | --- |
| `SEARCHAPI_API_KEY` | Your SearchApi key. Read only on the server, inside `/api/*` route handlers. |

### Run

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000). Other scripts: `npm run build`, `npm run start` and `npm run lint`.

## How it works

```text
User inputs: origin, destination, earliest departure, latest departure, length of stay
   |
   v
POST /api/calendar (Next.js route handler)
   - validates inputs (outbound window of 30 days or less)
   - computes UTC return bounds: [start + duration] to [end + duration]
   - calls SearchApi (google_flights_calendar)
   |
   v
Filter and rank
   - drops entries with missing prices or has_no_flights: true
   - keeps combinations where (return date - departure date) equals the length of stay
   - sorts by price, cheapest first
   - builds Google Flights deep links
   |
   v
Results UI: ranked cards with the lowest fare badge, dates and the inspect link
```

Notes:

- **Departure window vs. return date**: earliest and latest departure define the outbound window. The return date is the departure date plus the length of stay.
- **30-day limit**: Google Flights Calendar returns an outbound by return matrix, so the server caps the outbound window at 30 days to avoid timeouts and credit exhaustion.
- **UTC dates**: `addDays` and `dayDiff` in `src/lib/format.ts` use UTC timestamps.
- **Airport codes**: locations can be selected as "London (LHR)" or typed as "LHR". `extractAirportCode()` resolves both to the 3-letter IATA code.

### API routes

`POST /api/calendar` searches flexible round-trip fares for a trip duration.

```json
{
  "origin": "JFK",
  "destination": "LHR",
  "departAfter": "2026-11-01",
  "departBefore": "2026-11-20",
  "durationDays": 7
}
```

The response has `fares` (each with `id`, `fromCode`, `toCode`, `date`, `returnDate`, `priceUsd`, `inspectUrl` and nullable `airline`, `durationMinutes`, `stops`), `totalFound` and `requestedDuration`.

`POST /api/location` returns city and airport suggestions with IATA codes.

```json
{
  "query": "London",
  "departure": false
}
```

### Project structure

```text
frontend/src/
  app/api/calendar/route.ts   Fetch and filter calendar fares
  app/api/location/route.ts   Airport and city autocomplete
  app/page.tsx                Renders CheapestDayFinder
  components/                 CheapestDayFinder, SearchForm, LocationAutocomplete,
                              ResultsPanel, FareRow, FareRowSkeleton, Field, Button
  lib/                        types.ts, format.ts (UTC date math), cn.ts
```

## Resources

- [Live demo](https://cheapest-fly-date-finder.vercel.app): deployed version of this app.
- [SearchApi](https://www.searchapi.io/?utm_source=Dev&utm_medium=Ambassador&utm_campaign=studio1hq.com): the Google Flights API used here.

<br />

---

<div align="center">

<a href="https://studio1hq.com">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Studio1HQ/website/main/brand/studio1-logo-on-dark.svg" />
    <img src="https://raw.githubusercontent.com/Studio1HQ/website/main/brand/studio1-logo-on-light.svg" alt="Studio1" width="160" />
  </picture>
</a>

Built by **[Studio1](https://studio1hq.com)**, the technical content and DevRel partner for devtool teams. Made with [SearchApi](https://www.searchapi.io).<br />
Browse more open-source examples at [github.com/Studio1HQ](https://github.com/Studio1HQ).

[![Website](https://img.shields.io/badge/studio1hq.com-0b0807?style=for-the-badge&logo=googlechrome&logoColor=white)](https://studio1hq.com)
[![Book a call](https://img.shields.io/badge/Book_a_strategy_call-f97316?style=for-the-badge&logo=googlecalendar&logoColor=white)](https://cal.com/studio1/collab)
[![X](https://img.shields.io/badge/%40Studio1HQ-141414?style=for-the-badge&logo=x&logoColor=white)](https://x.com/Studio1HQ)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0a66c2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/company/studio1hq/)

<sub><a href="https://studio1hq.com">studio1hq.com</a> · Technical content, docs, video and DevRel for devtools</sub>

</div>
