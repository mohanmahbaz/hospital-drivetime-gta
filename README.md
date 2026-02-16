# Hospital Drive-Time Accessibility & Older Adults (65+) — GTA (GIS Day 2025 + DA Update)

This project maps **hospital drive-time accessibility** across the Greater Toronto Area (GTA) and compares it with the spatial distribution of **older adults (age 65+)** to highlight areas where higher senior populations may face longer travel times to hospitals.

**Presented:** GIS Day 2025 (UW)  
**Author:** Mohan Mahbaz  
**Tools:** ArcGIS Pro (Network Analyst – Service Area), Beyond 20/20 (table extraction)

---

## Map preview (updated DA version)
![Hospital drive time and 65+ per 1,000 (DA)](final_map_layout_2026.png)


---

## Research question
**How does hospital access (by driving time) vary across the GTA, and how does this pattern intersect with the distribution of adults aged 65+?**

---

## Data sources
- **Population (Age 65+) + DA boundaries:** Statistics Canada, 2016 Census of Population  
- **Road network:** Statistics Canada, 2016 Road Network File (RNF)  
- **Hospital locations:** Ontario Ministry of Health (MOH) hospital locations  
- **Coordinate system:** EPSG:26917 (NAD83 / UTM Zone 17N)

---

## Methods (high-level workflow)
1. **Prepared inputs**
   - Cleaned hospital point locations and clipped study area to the GTA.
   - Loaded the 2016 road network for network-based travel modeling.

2. **Service area (drive-time) analysis**
   - Generated hospital catchments using Network Analyst **Service Areas** at:
     - **0–5 minutes**
     - **5–10 minutes**
     - **10–15 minutes**

3. **Older adult metric**
   - Calculated **Age 65+ per 1,000 residents** at the Dissemination Area (DA) level:
     - `(Age 65+ / Total population) * 1000`

4. **Overlay + cartographic design**
   - Overlaid drive-time service areas on the DA choropleth.
   - Designed final print layout (legend, north arrow, scale bar, data notes).

---

## Iteration & improvement (feedback-driven update)
The original GIS Day 2025 version used a more aggregated geography. After feedback from **Dr. Tan**, I revised the analysis to address **MAUP (Modifiable Areal Unit Problem)** and improve interpretability:

### What changed
- **Geography:** moved from larger census units to **Dissemination Areas (DA)** (finer spatial resolution).
- **Metric:** replaced “% age 65+” with **65+ per 1,000 residents** to support clearer comparison across areas.
- **Data handling:** used **Beyond 20/20** to extract DA-level tables in smaller sections to avoid ArcGIS instability/crashes from very large full extracts.

### Why it matters
DA-level mapping reduces aggregation bias and reveals local patterns that can be hidden when using larger boundaries.

---

## Key takeaway (visual interpretation)
Central GTA shows stronger hospital coverage within shorter drive times, while outer areas may require longer travel time—especially important where DA-level 65+ concentration is higher.

---

## Limitations
- Drive-time results depend on road network assumptions (e.g., speeds/connectivity).
- No live traffic or time-of-day congestion modeled.
- Using 2016 census/network data may miss recent changes in population and infrastructure.

---

## Files in this repository
- `final_map_layout_2026.png` — updated DA-level map layout (final)
- `README.md` — project documentation

---

## Credits / licensing
Census boundary and demographic data © Statistics Canada (2016).  
Hospital locations: Ontario Ministry of Health (MOH).  
Road Network File (RNF): Statistics Canada (2016).

