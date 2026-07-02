# Soil Erosion Risk Assessment & Dam Siltation Decision Support — Upper Lebene Wadi Watershed, Northern Morocco

**A GIS-based multisource geospatial framework for erosion hazard mapping and siltation risk management in support of the Sidi Abou Dam (Morocco's National Water Resources Plan)**

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Method](https://img.shields.io/badge/methodology-PAP%2FRAC-blue)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Platform](https://img.shields.io/badge/GIS-QGIS%20%7C%20Google%20Earth%20Engine-orange)

---

## Overview

This project delivers a **spatial decision-support tool** for identifying, mapping, and prioritizing soil erosion risk in the upper **Lebene Wadi Watershed (L2W)**, Northern Morocco — a critical catchment feeding the strategic **Sidi Abou Dam**, currently under construction as part of Morocco's National Water Resources Plan (PNRE).

By integrating multisource geospatial data (satellite imagery, DEM, geological and land cover mapping) within the **PAP/RAC (Priority Actions Program / Regional Activity Center)** framework — a methodology developed under the UNEP Mediterranean Action Plan — this project produces actionable erosion risk maps to guide watershed management, soil conservation planning, and reservoir siltation mitigation.

The dam is expected to secure drinking water supply, irrigate ~5,000 hectares of farmland, and reduce downstream flood risk. Protecting its long-term storage capacity from sediment accumulation depends directly on identifying and managing upstream erosion sources — which is the core objective of this work.

---

## Objectives

- Quantify and spatially map **soil erosion vulnerability** across the upper L2W
- Identify and classify **erosion landforms** (sheet, rill, gully erosion)
- Detect **priority intervention zones** for soil conservation and watershed management
- Provide **spatial decision-support outputs** to reduce sediment yield and limit Sidi Abou Dam siltation
- Demonstrate a **replicable geospatial workflow** applicable to other Mediterranean watersheds

---

## Study Area

The upper L2W is located in the Central Rif Mountains, Fez-Meknes region, spanning the provinces of Taza and Taounate, Northern Morocco. Ouerrha Wadi delimits the basin to the north, Inaouen Wadi to the east and south, and the Sebou basin to the west. The basin is characterized by complex tectonic geology (convergence of the African and Alboran plates), a Mediterranean climate (~1000 mm/year in the north, ~500 mm/year in the south), and steep, erosion-prone terrain concentrated in its northern reaches.

![Study Area Location](maps/fig1_study_area_location.png)
*Figure 1 — Placement of the upper L2W within the Sebou basin and Morocco*

![Geological Structure](maps/fig2_geological_structure.png)
*Figure 2 — Geological structure of the upper L2W (Source: Suter & Mattauer, 1964)*

---

## Methodology — PAP/RAC Approach

This project applies the **PAP/RAC qualitative erosion risk model**, structured in three phases:

| Phase | Description |
|---|---|
| **Predictive** | Erosion risk modeling via overlay of lithological friability, slope, land cover, and vegetation protection layers |
| **Descriptive** | Mapping and field validation of current erosion landforms (sheet, rill, gully) |
| **Integrated** | Overlay of predicted erosion states with observed erosion forms to produce a final, validated risk map |

![PAP/RAC Method Workflow](maps/fig3_papra_method_workflow.png)
*Figure 3 — Method illustrating the guidelines of the PAP/RAC approach*

### Geospatial Data & Tools

- **DEM:** COPERNICUS DEM_WGS_1984 (30 m resolution) — slope classification
- **Satellite Imagery:** Harmonized Sentinel-2 MSI Level-2A (SR), 10 m resolution (15/02/2025, USGS) — NDVI, land cover classification
- **Classification:** Random Forest supervised classification (Google Earth Engine) using spectral bands (B2, B3, B4, NIR, SWIR1, SWIR2) and spectral indices (NDVI, MNDWI, NDBI, EVI, SAVI, BSI); 150 training samples per class
- **Geological Mapping:** 1/50,000 Rif geological map, Morocco (Suter, 1980) — lithological friability classification
- **Field Validation:** Ground-truthing via field survey, Google Earth Pro, Google Earth Engine
- **GIS Platform:** QGIS — spatial overlay, cartographic modeling, map production

---

## Results

### 1. Terrain Erodibility

**Lithological friability** — 71.86% of the basin has moderate friability (detrital/non-cohesive materials), concentrated in the southwestern parts near the hydrographic network.

| Lithological Class | Geological Formation | Extent (km²) | Extent (%) |
|---|---|---|---|
| Very high | Weakly / moderately compacted rocks | 15.97 | 4.53 |
| High | Slightly resistant rocks | 55.42 | 15.74 |
| Moderate | Detrital materials / non-cohesive rocks | 252.89 | 71.86 |
| Very low | Compact rock / crude minerals | 8.62 | 2.34 |
| Low | Moderately altered rock | 18.82 | 5.34 |

![Lithological Friability Map](maps/fig4_lithological_friability.png)
*Figure 4 — Lithological friability of formations in the upper L2W*

**Slope classes** — Strong to steep slopes dominate (72.71% combined), concentrated in the mountainous north.

| Slope Class | Slope Type (%) | Extent (km²) | Extent (%) |
|---|---|---|---|
| Extreme | >35 | 7.85 | 2.23 |
| Strong | 20–35 | 117.06 | 33.26 |
| Steep | 12–20 | 131.00 | 37.22 |
| Moderate | 3–12 | 86.64 | 24.61 |
| Low | 0–3 | 9.26 | 2.61 |

![Slope Classes Map](maps/fig5_slope_classes.png)
*Figure 5 — Slope classes in the upper L2W*

**Erodibility** — Combining lithological friability and slope gradient, moderate-to-strong erodibility dominates the basin (97% combined).

| Erodibility Class | Extent (km²) | Extent (%) |
|---|---|---|
| Very strong | 5.24 | 1.48 |
| Strong | 144.89 | 41.17 |
| Moderate | 196.66 | 55.88 |
| Weak | 14.05 | 3.99 |
| Very weak | 0.08 | 0.02 |

![Erodibility Map](maps/fig6_erodibility_map.png)
*Figure 6 — Erodibility classes in the upper L2W*

---

### 2. Soil Protection

**Land cover** — Forest/Matorral (30.02%) and tree farming (29.11%) dominate; agricultural activities and barren lands each cover ~20%.

| Land Cover | Extent (km²) | Extent (%) |
|---|---|---|
| Barren lands | 72.88 | 20.70 |
| Agricultural activities | 70.83 | 20.12 |
| Tree farming | 102.45 | 29.11 |
| Forest / Matorral | 105.66 | 30.02 |

![Land Cover Map](maps/fig7_land_cover_map.png)
*Figure 7 — Land cover classes in the upper L2W*

**Vegetation cover density** — Moderate density (50–75%) dominates the basin (51.23%).

| Vegetation Density Class | Extent (km²) | Extent (%) |
|---|---|---|
| >75% | 9.64 | 2.73 |
| 50–75% | 180.30 | 51.23 |
| 25–50% | 161.84 | 46.10 |
| <25% | 0.17 | 0.0004 |

![Vegetation Density Map](maps/fig8_vegetation_density_map.png)
*Figure 8 — Vegetation density classes in the upper L2W*

**Soil protection** — Nearly half the basin (47.9%) has low-to-very-low protection, concentrated in the south and near watercourses.

| Soil Protection Class | Extent (km²) | Extent (%) |
|---|---|---|
| Very high | 29.97 | 8.51 |
| High | 67.78 | 19.26 |
| Moderate | 85.66 | 24.34 |
| Low | 94.35 | 26.81 |
| Very low | 74.21 | 21.08 |

![Soil Protection Map](maps/fig9_soil_protection_map.png)
*Figure 9 — Soil protection classes in the upper L2W*

---

### 3. Erosion Risk Classification

| Erosion State | Extent (km²) | Extent (%) |
|---|---|---|
| Very high | 69.24 | 19.67 |
| High | 69.48 | 19.74 |
| Moderate | 74.82 | 21.26 |
| Low | 68.54 | 19.47 |
| Very low | 68.84 | 19.56 |

**→ Summary: 35% high-to-very-high risk · 12% moderate risk (partially overlapping classes above per basin-wide synthesis) · 52% low-to-very-low (stable)**

![Erosion State Map](maps/fig10_erosion_state_map.png)
*Figure 10 — Erosion state in the upper L2W basin*

---

### 4. Erosion Landforms

Sheet erosion is the most widespread active erosion form; gully erosion, though limited in area, is the primary sediment contributor.

| Erosion Form | Extent (km²) | Extent (%) |
|---|---|---|
| Gully erosion | 45.88 | 13.03 |
| Rill erosion | 92.02 | 26.14 |
| Sheet erosion | 94.98 | 26.98 |
| Stable areas | 119.00 | 33.81 |

![Erosion Forms Map](maps/fig11_erosion_forms_map.png)
*Figure 11 — Erosion forms in the upper L2W*

![Erosion Intensity Field Photos](maps/fig12_erosion_intensity_field.png)
*Figure 12 — Erosion intensity in the upper L2W (field observations, Google Earth 2025)*

![Erosion Forms per Risk Class](maps/fig13_erosion_forms_per_risk_class.png)
*Figure 13 — Erosion forms inside each erosion risk class*

![Integrated Erosion Map](maps/fig14_integrated_erosion_map.png)
*Figure 14 — Integrated map of erosion intensity and erosion forms in the upper L2W*

---

### 5. Cross-Tabulated Analysis

**Erosion severity by slope class (%)**

| Erosion State | Low | Moderate | Steep | Strong | Extreme |
|---|---|---|---|---|---|
| Very low | 4.17 | 35.40 | 38.94 | 19.61 | 1.88 |
| Low | 3.09 | 28.36 | 37.80 | 28.69 | 2.07 |
| Moderate | 2.57 | 21.72 | 36.08 | 37.17 | 2.46 |
| High | 2.52 | 19.72 | 35.66 | 39.56 | 2.54 |
| Very high | 1.79 | 17.52 | 37.37 | 40.39 | 2.93 |

**Erosion state by land cover (%)**

| Erosion State | Barren Land | Agricultural | Tree Farming | Forest/Matorral |
|---|---|---|---|---|
| Very high | 28.84 | 44.43 | 19.23 | 7.51 |
| High | 26.95 | 28.03 | 31.05 | 13.97 |
| Moderate | 22.06 | 16.24 | 36.97 | 24.73 |
| Low | 15.14 | 8.65 | 33.56 | 42.65 |
| Very low | 11.00 | 3.34 | 24.50 | 61.15 |

**Erosion state by lithological friability (%)**

| Erosion State | Very Low | Low | Moderate | High | Very High |
|---|---|---|---|---|---|
| Very high | 5.10 | 1.49 | 64.80 | 22.68 | 5.92 |
| High | 4.93 | 1.99 | 66.98 | 20.29 | 5.82 |
| Moderate | 4.55 | 2.42 | 70.60 | 17.43 | 5.00 |
| Low | 4.80 | 2.78 | 76.22 | 12.41 | 3.79 |
| Very low | 7.19 | 3.12 | 81.77 | 5.75 | 2.17 |

---

## Decision Support Applications

This geospatial framework is designed to directly inform:

- **Prioritization** of soil conservation interventions (reforestation, contour farming, vegetation buffer strips) — priority focus on the **northern L2W**, where >70% of gully and rill erosion landforms concentrate in high-to-extreme erosion zones
- **Siting** of sediment control structures (check dams, gabions, retention basins) to reduce sediment connectivity to the hydrographic network
- **Land use planning** to limit unsustainable agricultural practices (deep tillage, overgrazing) on high-risk slopes
- **Long-term reservoir management** by projecting sediment yield and siltation risk to the Sidi Abou Dam

---

## Repository Structure

```
├── data/               # Input datasets (DEM, Sentinel-2, geological maps)
├── gis_processing/     # QGIS project files, GEE scripts, classification models
├── maps/               # Output erosion risk & land cover maps (raster/vector) — Figures 1–14
├── report/             # Full study report and figures
└── README.md
```

> **Note:** Add your exported map images to a `maps/` folder in this repository, matching the filenames referenced above (e.g. `fig4_lithological_friability.png`), and they will render automatically in this README.

---

## References & Methodology Source

- Priority Actions Program Regional Activity Center (PAP/RAC), UNEP Mediterranean Action Plan (PLAN, 1997)
- Suter, G. (1980). *Geological Map of the Rif, Morocco, 1/50,000*
- Suter, G. & Mattauer, M. (1964). Geological structure of the Rif
- Copernicus DEM & Sentinel-2 MSI (ESA/USGS)

---

## License

This project is licensed under the **MIT License**.

## Author

**Achraf Samyhouari** — Geospatial Analysis, GIS & Remote Sensing

---

*Keywords: Soil Erosion, Dam Siltation, PAP/RAC, GIS, Remote Sensing, Google Earth Engine, Watershed Management, Decision Support, Northern Morocco*
