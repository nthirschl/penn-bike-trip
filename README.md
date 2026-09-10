# Pennsylvania Trip

## Overview
A four-day bike trip through the Pine Creek Gorge — the "Pennsylvania Grand Canyon" — October 15–18, 2026.
Drive in Thursday, ride a 3-day loop out of Jersey Shore, PA, drive home Sunday.

## Riders
- **Noah**
- **Andy** (brother)
- **Nico** (brother)
- **Dad**

## The Ride
A 76.97 mi loop out of Jersey Shore, split across three days by where the Airbnbs sit.

| Day | Date | Leg | Distance | Gain |
|-----|------|-----|----------|------|
| 1 | Fri, Oct 16 | Jersey Shore → Morris | ~40.7 mi | ~2,750 ft |
| 2 | Sat, Oct 17 | Morris → Ramsey Drive | ~34.0 mi | ~550 ft |
| 3 | Sun, Oct 18 | Ramsey Drive → Jersey Shore | ~8.4 mi | ~200 ft |
| | | **Total** | **~83 mi** | **~3,500 ft** |

Day 1 carries essentially all the climbing: up over the plateau to a high point of 1,975 ft
around mile 28.6, then down to Blackwell and east along Babb Creek to Morris. Days 2 and 3 are
the Pine Creek Rail Trail — flat crushed limestone, gently downhill the whole way.

Day 2 is the short, flat day and the natural place to add mileage if we want it.

## Project Structure
- `bike-route/` — GPX tracks: the original full loop plus per-day splits and the Morris connector
- `accommodations/` — Airbnb booking PDFs and lodging details
- `itineraries/` — Daily schedules and travel plans
- `points-of-interest/` — Stops, food, overlooks, swimming holes

## Site
- `index.html` — Landing page
- `timeline.html` — Day-by-day schedule
- `map.html` — Interactive Leaflet map: route colored by day, Airbnbs, parking, POIs
- `styles.css` — Shared theme

## How the distances were calculated
1. Parsed `bike-route/Hirschl_family_bike_ride_october__26.gpx` (3,888 track points) and computed
   cumulative haversine distance. Result: 76.89 mi, against RideWithGPS's official 76.97 mi.
2. Geocoded all three Airbnb addresses with the US Census geocoder.
3. Found the closest track point to each Airbnb to get the split miles:
   - **Happy Mountain Camp** (271 Ramsey Dr) sits 0.06 mi off the trail at mile 68.5 of the loop —
     leaving 8.4 mi back to the cars. That matches the "about 10 mi" estimate.
   - **Sweet Side Cottage** (Morris) is 2.9 mi beyond the route's northern turnaround at mile 37.6.
     Road-routed via OSRM, that connector is **3.1 mi** on PA-414/PA-287 — ridden out Friday and
     back Saturday, so ~6.2 mi total on top of the loop.
   - **Our Neck of the Woods** (Rauchtown Rd) is off-route to the south — Thursday night only,
     12.6 mi by road from the Jersey Shore trailhead.
4. Elevation gain: the raw GPX sums to 4,837 ft, which is GPS noise. A 3 m threshold filter gives
   3,263 ft against RideWithGPS's official 3,293 ft, so per-day figures use that method scaled to
   the official total.

## Conventions
- Dates use `YYYY-MM-DD` format.
- Currency in USD.
- Coordinates stored as `lat, lng` decimal degrees.
- Distances in miles, elevation in feet.
- All data files use Markdown unless a specific format (GPX, GeoJSON) is more appropriate.
