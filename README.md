# DamGuard Nexus 🌊

### AI-Powered Multi-Basin Dam Break & Inundation Intelligence

DamGuard Nexus is a web-based decision-support platform that simulates dam-break floods on real terrain and turns the results into actionable information for district administrations: **who gets hit first, how fast, and where to evacuate.**

> Built for Smart India Hackathon 2026.

---

## 🎥 Demo

- **Demo video:** _add YouTube link here_
- **Live demo:** _add GitHub Pages link here_

---

## ❗ Problem

India has thousands of large dams, and many communities live directly below them. When a dam fails, floodwater reaches downstream villages within minutes, but warnings still depend on manual estimates, scattered data and slow communication. Officials do not know which village is hit first, how deep the water will be, or which route is safe.

## ✅ Solution

DamGuard Nexus takes real terrain (DEM) and live telemetry, simulates the breach, predicts flood arrival village by village, and generates evacuation routes, GIS layers, advisory documents and multilingual alerts, in minutes, not hours.

---

## ✨ Key Features

| Feature | What it does |
|---|---|
| **Basin Telemetry Network** | Lists monitored dams with reservoir levels and loads live readings into the simulation |
| **Live Weather Data** | Rain, wind and river discharge from Open-Meteo, refreshed every 5 minutes |
| **Simulation Controls** | Set reservoir level, upstream inflow and failure trigger (e.g. overtopping); breach width and peak discharge are calculated automatically |
| **Hydro Flow** | Real-time flood wave moving down the river, village-wise arrival countdown and live residents-affected counter |
| **Playback Controls** | Pause, reset, and 0.5x / 1x / 2x / 4x speed |
| **Emergency Siren** | Starts automatically when the simulation starts; can be muted anytime |
| **Velocity Heatmap** | Flow speed shown as a colour scale (green = slow → yellow → orange → red = fastest) |
| **Evacuation Routes** | Flooded zone in red, gold routes from each village to safe assembly points on higher ground |
| **Analysis Panel** | Monte Carlo flood probability map, Sentinel-1 flood mapping and hindcast (Google Earth Engine), and support for any river with custom location or DEM |
| **Collector Advisory PDF** | One-click flood advisory with situation summary, telemetry, breach scenario and threat level |
| **GIS Export** | Depth-classified inundation layers in KML, GeoJSON and Shapefile |
| **Data Files** | DEM, river profile, hydrograph, max-depth grid, village arrivals, telemetry log |
| **Loss Analysis** | Buildings, hospitals, schools, roads and bridges from OpenStreetMap with depth-damage curves |
| **Alert Dispatch** | CAP 1.2 alerts and SMS in English, Hindi and Telugu, bundled as a zip |
| **Model Comparison** | SPH-hybrid vs pure shallow-water (SWE) vs imported Delft3D result |
| **Multi-Basin** | Srisailam (Krishna Basin), Rishiganga (Alaknanda Basin), Kosi Barrage (Bihar) |

---

## 📸 Screenshots

Put your screenshots in a `screenshots/` folder and rename them as below.

| | |
|---|---|
| ![Dashboard](screenshots/01-dashboard.jpeg) **Dashboard & telemetry** | ![Breach start](screenshots/02-breach-start.jpeg) **Breach execution** |
| ![Flood front](screenshots/03-flood-front.jpeg) **Hydro Flow: flood front** | ![All clusters](screenshots/04-all-clusters.jpeg) **All village clusters hit** |
| ![Velocity heatmap](screenshots/05-velocity-heatmap.jpeg) **Velocity Heatmap** | ![Evacuation](screenshots/06-evacuation-routes.jpeg) **Evacuation Routes** |
| ![Analysis](screenshots/07-analysis.jpeg) **Analysis panel** | ![Advisory](screenshots/08-collector-advisory.jpeg) **Collector Advisory PDF** |
| ![GIS](screenshots/09-gis-export.jpeg) **GIS export** | ![Data files](screenshots/10-data-files.jpeg) **Data files** |
| ![Alerts](screenshots/11-alerts-sms.jpeg) **Multilingual SMS alerts** | ![CAP](screenshots/12-cap-compare.jpeg) **CAP 1.2 alert & model comparison** |
| ![Multi-basin](screenshots/13-multi-basin.jpeg) **Multi-basin switch** | |

---

## 🧰 Tech & Data Sources

- **Terrain:** AWS Terrarium DEM (z12)
- **Flood solver:** 2D shallow-water equations (SWE), with near-field SPH-hybrid comparison
- **Breach model:** Froehlich (2008) breach width/time, Froehlich (1995) peak discharge
- **Live data:** Open-Meteo (rain, wind, river discharge)
- **Facilities & roads:** OpenStreetMap (Overpass API)
- **Satellite validation:** Sentinel-1 via Google Earth Engine
- **Alert format:** CAP 1.2 (OASIS) + SMS in EN / HI / TE
- **Export formats:** KML, GeoJSON, Shapefile, CSV, ASC, PDF
- **Frontend:** HTML, CSS, JavaScript (single-file web app, runs fully in the browser)

---

## 🚀 How to Run

1. Download `damguard-nexus-final-v2.html` (rename to `index.html` for GitHub Pages).
2. Open it in any modern browser. No installation needed.
3. Select a dam and basin from the top bar.
4. Adjust reservoir level, inflow and failure trigger.
5. Click **Execute dynamic breach & flow**.
6. Switch between **Hydro Flow**, **Velocity Heatmap** and **Evacuation Routes**.
7. Use **Analysis**, **Download collector advisory PDF**, **Export GIS** and **Data files** for outputs.

An internet connection is needed for the base map imagery and live Open-Meteo data.

---

## 🔬 Validation Notes

- **Monte Carlo:** 200-500 runs varying breach width, breach time and Manning's n to produce a flood probability map.
- **Sentinel-1 hindcast:** runs in the user's own Earth Engine account; polygons are exported there and imported here as GeoJSON.
- **Hindcast caveat:** the February 2021 Rishiganga event was a rock-ice avalanche and debris flood, not a dam breach, so it is only an analogue and a low IoU is expected.

---

## ⚠️ Disclaimer

Flood results are **simulated screening estimates** for planning and demonstration. They are not an official warning. Damage estimates use approximate depth-damage curves and are not a survey. Generated alerts are marked as exercise/simulation.

---

## 👥 Team

_Add team name and members here._

**Smart India Hackathon 2026** · Problem Statement: _add PS ID here_

---

## 📄 License

_Add license (e.g. MIT) here._
