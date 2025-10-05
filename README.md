# FloraCast

A dynamic, web-based visualization and analytics platform that leverages NASA Earth observation data (e.g., **MODIS, Landsat, VIIRS**) to detect and display flowering intensity, timing, and spatial patterns. Users can explore seasonal/annual bloom dynamics on an interactive global map, zoom into regions of interest, and inspect time-series trends. The platform combines **NDVI/EVI** with **temperature, precipitation, wind** and other climate drivers to interpret bloom events, and adds ecological modules for pollinators, invasive species, aridity, and interannual trends.

---

## What the platform does

* **Visual Data Layers**
  Date-selectable global layers: satellite true color, temperature, precipitation, and **NDVI/EVI**. A **dual-map compare** mode lets you place two dates/sensors/variables side-by-side for rapid visual analysis.

* **Flower Photos**
  Shows real flower photos near any selected point (e.g., from iNaturalist). Time filters reveal seasonal patterns across the year.

* **Vegetation Indices**
  Retrieves precise **NDVI/EVI** values at the clicked location for detailed inspection. You can also aggregate by “point + radius” to build annual curves for a local region.

* **Rainfall · Aridity · Superbloom**
  Uses **NASA POWER** rainfall over the past 365 days to compute recent-share rainfall and an aridity indicator—an **heuristic “superbloom likelihood”** signal.

* **Pollinator Dynamics**
  Pulls iNaturalist observations by user-provided taxon IDs (multiple allowed) to compare pollinator activity against the local bloom trajectory and assess plant–pollinator synchrony.

* **Invasive Species**
  Analyzes the last five years of iNaturalist observations: ranks species by counts and highlights introduced/potentially invasive risks with simple trend flags.

* **Phenology & Predictions (Rule-Based)**
  Estimates **bloom onset and flowering windows** (e.g., cherry, rose) using **Base Temperature** and **GDD Threshold**; users can supply custom parameters for specific species/cultivars.

* **Weather**
  Fetches temperature and precipitation for any location/date and plots recent statistics (e.g., last 30 days) with sensible missing-data handling.

* **Machine Learning (Lightweight)**
  Trains on multi-year historical data to **forecast NDVI/EVI** short-term trends using least-squares regression (and optionally a tiny MLP if TF.js is loaded).

* **AI Assistant**
  Via the ChatGPT API, reads local context and produces planting recommendations (what to grow, sowing windows, irrigation, risks). Users can ask follow-ups for tailored guidance.

---

## Objectives

Unify NASA satellite data and ground observations into an approachable tool for monitoring, explaining, and (optionally) predicting flowering dynamics. Support climate–vegetation studies, pollinator synchrony, invasive spread awareness, and practical planning for agriculture, urban greening, tourism, and public health—so decisions are **data-driven and reproducible**.

---

## Tech & Tools

* **Frontend:** HTML, CSS, JavaScript; **Leaflet** (maps), **Plotly** (charts)
* **APIs & Data:** NASA **GIBS** (imagery/indices), NASA **POWER** (daily meteorology), **iNaturalist**, **OpenPortGuide** (where used), **OpenStreetMap Tiles** & **Nominatim**
* **AI:** OpenAI ChatGPT API (for explanations and Q&A)
* **Hosting:** GitHub Pages (static)

---

## Use of AI

* ChatGPT (for debugging help, drafting, and content refinement)
* **Machine Learning:** client-side **least-squares linear regression** (normal equation); optional **TensorFlow.js** MLP for mild nonlinearity
* **Prompts/API:** OpenAI ChatGPT

---

## Data Sources

* **NASA GIBS:** [https://gibs.earthdata.nasa.gov](https://gibs.earthdata.nasa.gov)
* **NASA POWER:** [https://power.larc.nasa.gov](https://power.larc.nasa.gov)
* **iNaturalist:** [https://www.inaturalist.org](https://www.inaturalist.org)
* **OpenPortGuide:** [https://weather.openportguide.de](https://weather.openportguide.de)
* **OpenStreetMap Tiles:** [https://www.openstreetmap.org](https://www.openstreetmap.org)
* **OSM Nominatim:** [https://nominatim.openstreetmap.org](https://nominatim.openstreetmap.org)

> Please follow each provider’s attribution and terms of use.
