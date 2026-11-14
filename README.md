# MARSWALK

Single-page Mars exploration planner (NASA Space Apps Challenge 2026 – Martian Map).

## Files
- `index.html` – the whole app
- `mola_grid.json` – small elevation grid (you create it once, see below). Without it the app still works; the elevation profile just says "unavailable".
- `make_mola_grid.py` – script that creates `mola_grid.json` from NASA/USGS MOLA data

## Put it online (GitHub Pages)
1. Upload `index.html`, `README.md`, `make_mola_grid.py` (and `mola_grid.json` once you have it) to a repository.
2. Settings → Pages → Deploy from a branch → `main` / root.

## Add the elevation data (one time)
Follow the steps at the top of `make_mola_grid.py`, then upload the `mola_grid.json` it creates next to `index.html`.
Note: opening `index.html` by double-click blocks the file load in most browsers; test through GitHub Pages or with `python -m http.server`.

## Data and honesty notes
- Imagery: Viking MDIM 2.1 colour mosaic via NASA Trek. Relief layer: MGS MOLA via NASA Trek (layer names are set at the top of the script and can be changed).
- Elevation: MGS MOLA gridded topography (PDS / USGS), downsampled to a coarse grid.
- Distances are great-circle on a sphere (R = 3389.5 km). Direct routes are never called safe; local slopes and hazards are not modelled.
- Landmarks are approximate IAU reference coordinates, not instrument observations.
