MARSWALK
An Interplanetary Survival Guide --- Martian Map
MARSWALK is a browser-based Mars exploration planning tool created for
the NASA Space Apps Challenge 2026 challenge, "Interplanetary
Survival Guide: Martian Map."

It lets users choose locations on a real Mars map, plan a direct route,
and explore regional elevation information. It also makes the limits of
the available data clear: a route on the map is not a safety
recommendation.
Project status: Prototype. Some NASA Trek map-layer endpoints
still need to be tested in the target browser. Read the limitations
below before interpreting the results.

Screenshots
Add screenshots of the working application to the screenshots/
folder, then replace the placeholders below with the matching image
paths.
1. Main map and route planner
<!-- Replace with: ![MARSWALK main map](screenshots/main-map.png) -->
Screenshot placeholder: Main map showing the selected start,
waypoints, destination, and route.
2. Elevation profile
<!-- Replace with: ![MARSWALK elevation profile](screenshots/elevation-profile.png) -->
Screenshot placeholder: Elevation profile showing regional elevation
and route statistics.
3. Mission briefing
<!-- Replace with: ![MARSWALK mission briefing](screenshots/mission-briefing.png) -->
Screenshot placeholder: Generated briefing with route details and
data limitations.
Features
- Mars map: Leaflet displays the Viking colour mosaic from NASA
  Trek. If the imagery cannot load, the app falls back to a
  latitude/longitude grid and reports that fallback in the status
  line.
- Route planning: Click the map to add a start point, waypoints,
  and a destination.
- Great-circle distance: Route distance is calculated along a
  spherical Mars model using a mean radius of 3,389.5 km. Routes
  crossing the map edge are drawn across the edge correctly.
- Elevation profile: Uses a coarse MOLA elevation grid to show the
  elevation range, total climb and descent, steepest regional
  gradient, and an estimated walking time.
- Map layers: Imagery, MOLA relief, coordinate grid, landmarks,
  and routes. A CRISM minerals layer slot exists, but CRISM data is
  not currently integrated.
- Science landmarks: Explore six reference locations: Jezero,
  Gale, Olympus Mons, Valles Marineris, Hellas, and Gusev.
- Search: Search by landmark name or coordinates, for example
  18.4, 77.6.
- Mission briefing: Generate a route briefing and print it to PDF
  or export route information as JSON or CSV.
- Saved routes: Routes can be saved in the browser.
- Convenience options: Switch between kilometres and miles, choose
  between two coordinate formats, and load example routes.
Data sources
  Data                    Source                  How MARSWALK uses it
  Mars imagery            Viking MDIM 2.1 colour  Base map imagery
mosaic via NASA Trek    

  Relief tiles            MGS MOLA via NASA Trek  Optional relief map
layer; exact layer
configuration still
needs verification

  Elevation values        MGS MOLA topography     Reduced to a coarse
from USGS / PDS         mola_grid.json file,
approximately 30 km per
cell
Landmarks               Approximate IAU         Reference points and
reference coordinates   short science
descriptions
The app does not use live rover telemetry or live Mars weather data.
Important scientific limitations
MARSWALK is an exploration-planning aid and educational prototype. It
does not determine whether a route is safe.
- A route is a direct great-circle path. It is not terrain-aware
  navigation.
- The elevation grid is coarse, at approximately 30 km per cell. It
  cannot represent local slopes, boulders, small craters, or other
  small-scale hazards.
- Walking time is an estimate based on an assumed pace and a
  flat-ground assumption. It is not a prediction of actual travel
  time.
- The steepest gradient is regional and depends on the resolution of
  the elevation grid. It should not be interpreted as a rover-scale or
  human-scale slope measurement.
- The NASA Trek imagery and relief tile addresses have not yet been
  fully verified in the target browser. If imagery fails, the app
  should show its grid fallback and status message.
- CRISM minerals data is not integrated; its layer slot is only a
  placeholder.
- Landmark coordinates are approximate reference coordinates.
Please do not use MARSWALK output as operational guidance for a real
crewed or robotic mission.
Run locally
You need Python 3 installed. No backend or package installation is
required for the described local workflow.
1. Put index.html and mola_grid.json in the same project folder.
2. Open a terminal in that folder.
3. Start a local static web server:
   python -m http.server 8000
4. Open this address in your browser:
   http://localhost:8000
Use the local server rather than double-clicking index.html. Browsers
can block the elevation file when the page is opened directly from the
filesystem.
Deploy with GitHub Pages
1. Create a GitHub repository for the project.
2. Upload index.html and mola_grid.json to the repository.
3. Add this README.md and any screenshots you want to show.
4. In the repository settings, enable GitHub Pages for the branch
   and folder containing index.html.
5. Open the published Pages URL and test the map, elevation profile,
   route planner, and exports.
Do not upload the original 2 GB source elevation file. The app uses
the reduced mola_grid.json file.
Project files
MARSWALK/
├── index.html          # Complete single-page application
├── mola_grid.json      # Reduced, coarse MOLA elevation grid
├── make_mola_grid.py   # Script used to create mola_grid.json
├── README.md           # Project documentation
└── screenshots/        # Optional screenshots for this README
Example screenshot folder:
screenshots/
├── main-map.png
├── elevation-profile.png
└── mission-briefing.png
Project goal
An astronaut needs to travel from a landing site to a science target.
MARSWALK displays a planned route on Mars imagery, uses MOLA elevation
data to show regional climbs and gradients, and clearly communicates
what the available data cannot tell us.

MARSWALK does not claim that a direct route is safe. It helps users
explore the map and understand the terrain data---with its limitations
in view.
Challenge
- Event: NASA Space Apps Challenge 2026
- Challenge: Interplanetary Survival Guide: Martian Map
- Project: MARSWALK
Add your team name, contributor names, repository URL, and deployed
demo URL here when they are available.
Credits and references
- NASA Trek --- Mars map and planetary data viewer:
  https://trek.nasa.gov/
- USGS Astrogeology --- planetary data and mapping resources:
  https://astrogeology.usgs.gov/
- NASA Planetary Data System (PDS): https://pds.nasa.gov/
- NASA Space Apps Challenge: https://www.spaceappschallenge.org/
Check the relevant dataset documentation and attribution requirements
when preparing the final public submission.
