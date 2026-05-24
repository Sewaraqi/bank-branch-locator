# Bank Branch Locator

A bilingual (Hebrew/English) React web application that helps users find Israeli bank branches — either by city or by proximity to their current location.

---

## Features

- **Search by City** — Enter a city name and get a full list of bank branches with addresses and phone numbers
- **Find Nearest Branches** — Select a bank, allow location access, and instantly see the 3 closest branches sorted by distance
- **Interactive Map** — Google Maps integration showing your location and branch markers with info windows
- **Bilingual UI** — Full Hebrew and English support with automatic RTL layout switching
---

## Getting Started

### Prerequisites

- **Node.js** v16 or higher
- **npm** v8 or higher
- A **Google Maps API key** with the Maps JavaScript API enabled

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/sewaraqi/bank-branch-locator.git
cd bank-branch-locator

# 2. Install dependencies
npm install

# 3. Configure environment variables
```

Create a `.env` file in the project root:

```env
REACT_APP_GOOGLE_MAPS_API_KEY=your_google_maps_api_key_here
```

### Running Locally

```bash
npm start
```

Opens the app at [http://localhost:3000](http://localhost:3000) with hot reload enabled.

### Running Tests

```bash
npm test
```

Launches Jest in interactive watch mode.

### Production Build

```bash
npm run build
```

Outputs an optimized, minified bundle to the `/build` directory, ready for deployment.

---

## Data Source

Branch data is fetched in real time from the **Israeli Government Open Data Portal**:

- **API**: `https://data.gov.il/api/3/action/datastore_search`
- **Resource ID**: `1c5bc716-8210-4ec7-85be-92e6271955c2`
- **Fields used**: bank name, branch name, city, address, phone, coordinates, accessibility

No backend is required — the app is fully client-side.

---

## Deployment

The app is deployed on **Netlify**. The `public/_redirects` file ensures all routes fall back to `index.html` for client-side navigation:

```
/*    /index.html   200
```

To deploy manually:

```bash
npm run build
# Upload the /build folder to Netlify, or connect your GitHub repo via the Netlify dashboard
```

---

## Environment Variables

| Variable | Description |
|---|---|
| `REACT_APP_GOOGLE_MAPS_API_KEY` | Google Maps JavaScript API key |

---

## Internationalization

The app supports **Hebrew** (default) and **English**. Language is auto-detected from the browser and can be toggled manually via the header. Translations live in `public/locales/{lang}/translation.json`.

RTL layout is applied automatically when Hebrew is active, using the MUI RTL theme and Emotion's Stylis RTL plugin.

---

