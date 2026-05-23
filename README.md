# Magical Paris Map 🏰✨

An interactive single-page map of Paris, styled after the Disneyland Paris
brand palette (twilight-castle navy, Maleficent purple, Minnie pink and
champagne gold). Built with [Leaflet](https://leafletjs.com/) — no build
step, no dependencies beyond a CDN, just open `index.html` in a browser.

## Features

- **70+ curated places** across four categories:
  - 🎠 Kids — Disneyland, Parc Astérix, Cité des Sciences, Jellycat Patisserie…
  - 🍽️ Lunch & Dinner — Bambini, Gigi, Noura, Candelaria, MUN…
  - ☕ Breakfast & Coffee — Ladurée, Carette, Pierre Hermé, Bacha, Ralph's…
  - ✨ Attractions — Louvre, Musée d'Orsay, Montmartre, Trocadéro, Opéra…
- **Filter by category** with a horizontally-scrollable button row.
- **Live search with full dropdown** — click the search box to see every place
  grouped by category, or type to filter; highlights matches.
- **Branch lists** — multi-location places (Ladurée, Angelina, Pierre Hermé,
  Noura, Bacha, Café Kitsuné, Mamiche, Buly 1803) show every address.
- **Rich popups** with description and one-tap links to Google Maps and
  TripAdvisor.
- **Live user location** with a pulsing pink marker, accuracy circle and the
  nearest place from your list (with distance).
- **Mobile-friendly** — dynamic viewport sizing, touch-optimised dropdown and
  popup, scroll-snap category bar, landscape phone layout.

## Run locally

Just open the file:

```bash
open index.html
```

Or serve it (recommended for testing geolocation on phones — iOS Safari blocks
GPS on `file://`):

```bash
python3 -m http.server 8000
# then visit http://localhost:8000 (or http://<your-ip>:8000 from your phone)
```

## Publish on GitHub Pages

Once this repo is on GitHub:

1. Go to **Settings → Pages**.
2. Under **Source**, select branch `main`, folder `/ (root)`.
3. Save. After ~30 seconds your map is live at
   `https://<your-username>.github.io/<repo-name>/`.

## Editing the place list

All data lives in the `PLACES` array near the top of the `<script>` block in
`index.html`. Each entry is:

```js
{
  name: "Place name",
  cat:  "kids" | "dining" | "coffee" | "attraction",
  lat:  48.8584, lng: 2.2945,
  desc: "Short description shown in the popup.",
  branches: [ "Branch 1 — address", "Branch 2 — address" ], // optional
  gmaps: "Google Maps search query",
  ta:    "TripAdvisor search query"
}
```

To recolour the brand, edit the CSS custom properties in `:root` at the top of
the file.

## Stack

- [Leaflet 1.9.4](https://leafletjs.com/) — open-source map library
- [CARTO Voyager](https://carto.com/basemaps/) tiles
- Google Fonts: Cinzel, Mr Dafoe, Quicksand
- Pure HTML + CSS + vanilla JS — no build step

## License

MIT — see [LICENSE](./LICENSE).
