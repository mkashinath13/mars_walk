<div align="center">

# 🔴 MARSWALK

### Plan a path across the Red Planet.

An interactive Mars exploration workspace for mapping destinations, planning direct routes, and exploring regional elevation—with the data’s limitations clearly in view.

[**Launch MARSWALK**](https://mkashinath13.github.io/mars_walk/) · [View the source](https://github.com/mkashinath13/mars_walk)

Built for the **NASA Space Apps Challenge 2026** · *Interplanetary Survival Guide: Martian Map*

</div>

---

## About

MARSWALK is a browser-based Mars route-planning prototype. Choose a starting point, add waypoints, and set a destination on a Mars map. Explore a coarse elevation profile and create a mission briefing to help understand the route.

> **Important:** MARSWALK is an educational exploration tool—not a navigation system or safety assessment. A direct route is not necessarily traversable or safe.

## What you can do

- **Explore Mars:** View a Viking colour mosaic map, with a coordinate-grid fallback if imagery is unavailable.
- **Plan a route:** Select a start, add waypoints, and choose a destination.
- **Review distance:** See great-circle distance calculated using a mean Mars radius of 3,389.5 km.
- **Inspect regional elevation:** View a coarse MOLA-based profile, elevation range, estimated climb and descent, and regional gradient.
- **Find places:** Search landmarks or coordinates, or explore six reference locations: Jezero, Gale, Olympus Mons, Valles Marineris, Hellas, and Gusev.
- **Create a briefing:** Print a mission briefing or export route data as JSON or CSV.
- **Save and customize:** Save routes in your browser, switch between kilometres and miles, choose a coordinate format, and load example routes.
- **Toggle map layers:** Explore imagery, MOLA relief, the coordinate grid, landmarks, and routes. The CRISM layer is a placeholder; CRISM data is not integrated.

## Try the live project

Open **[mkashinath13.github.io/mars_walk](https://mkashinath13.github.io/mars_walk/)** in your browser. No installation or account is required.

## Run locally

You’ll need Python 3. The app is a static website and does not require a backend or package installation.

1. Clone or download this repository.
2. Open a terminal in the project directory.
3. Start a local web server:

   ```bash
   python -m http.server 8000
   ```

4. Visit [http://localhost:8000](http://localhost:8000).

Use a local server instead of opening `index.html` directly; browsers may block the elevation data file when loaded from the filesystem.

## Data and sources

| Data | Source | Use in MARSWALK |
| --- | --- | --- |
| Mars imagery | Viking MDIM 2.1 colour mosaic via [NASA Trek](https://trek.nasa.gov/) | Base map |
| Relief tiles | MGS MOLA via NASA Trek | Optional relief layer; tile configuration may need verification |
| Elevation grid | MGS MOLA topography from [USGS / PDS](https://pds.nasa.gov/) | Reduced grid at approximately 30 km per cell |
| Landmarks | Approximate IAU reference coordinates | Reference points and short descriptions |

MARSWALK does **not** use live rover telemetry or live Mars weather data. The original source elevation file is not included; the app uses the reduced `mola_grid.json` file.

## Limitations

MARSWALK is a prototype for exploration and education. Keep these limitations in mind when interpreting its results:

- Routes are direct great-circle paths, not terrain-aware navigation.
- The elevation grid is coarse (approximately 30 km per cell) and cannot show local slopes, boulders, small craters, or other small-scale hazards.
- Walking time is an estimate based on an assumed pace and flat-ground conditions; it is not a prediction of actual travel time.
- The reported steepest gradient is regional and depends on grid resolution. It is not a rover-scale or human-scale slope measurement.
- NASA Trek imagery and relief tile endpoints may not work in every browser or environment. If imagery fails, the app is intended to show a coordinate-grid fallback and a status message.
- CRISM minerals data is not integrated, and landmark coordinates are approximate.

**Do not use MARSWALK output as operational guidance for a real crewed or robotic mission.**

## Project files

```text
mars_walk/
├── index.html          # Single-page application
├── mola_grid.json      # Reduced, coarse MOLA elevation grid
└── README.md
```

## Challenge and credits

Created for the [NASA Space Apps Challenge](https://www.spaceappschallenge.org/) challenge **“Interplanetary Survival Guide: Martian Map.”**

- [NASA Trek](https://trek.nasa.gov/) — Mars map and planetary data viewer
- [USGS Astrogeology](https://astrogeology.usgs.gov/) — planetary data and mapping resources
- [NASA Planetary Data System](https://pds.nasa.gov/)
- [NASA Space Apps Challenge](https://www.spaceappschallenge.org/)

Please consult the original dataset documentation for full attribution and usage details.
