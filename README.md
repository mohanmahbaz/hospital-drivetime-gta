# Hospital Drive-Time Access & Older Adults (65+) — GTA

This project maps how long it takes to drive to a hospital across the Greater Toronto Area (GTA) and compares that with where **older adults (age 65+)** live. The goal is to identify areas where seniors may have longer travel times to hospital care.

**Author:** Mohan Mahbaz  
**Presented:** GIS Day 2025 (UW)  
**Software:** ArcGIS Pro (Network Analyst), Beyond 20/20 (table download)

---

## Map (final layout)
![Hospital Drive Time & 65+ per 1,000 (DA)](Final%20map%20layout%202026.png)

---

## Presentation (GIS Day 2025)
- **Slides (PowerPoint):** [Download here](QGIS%20Day%20Presentation%20comp.pptx)  
  *(GitHub may not preview this in the browser because the file is large, but it downloads normally.)*

---

## Research question
**How does hospital access (by driving time) vary across the GTA, and how does this relate to where older adults (65+) live?**

---

## Data used
- **Population + boundaries (DA):** Statistics Canada, 2016 Census
- **Road network:** Statistics Canada, 2016 Road Network File (RNF)
- **Hospitals:** Ontario Ministry of Health hospital locations
- **Coordinate system:** NAD83 / UTM Zone 17N (EPSG:26917)

---

## What I did (method)
1. Loaded hospital locations and the GTA road network.
2. Used **Service Area (drive-time)** analysis from each hospital to create travel-time zones:
   - 0–5 minutes, 5–10 minutes, 10–15 minutes
3. Calculated **older adults per 1,000 residents** for each Dissemination Area (DA):
   - `(Age 65+ / Total population) * 1000`
4. Mapped the 65+ rate by DA and overlaid the hospital drive-time zones.

---

## Improvement after feedback (MAUP)
After feedback from **Dr. Tan**, I improved the analysis to reduce MAUP (Modifiable Areal Unit Problem):
- Switched to **Dissemination Areas (DA)** for finer detail (instead of larger census units).
- Used **65+ per 1,000 residents** instead of percent to support clearer comparison.
- Used **Beyond 20/20** to download DA-level census tables in manageable parts (large downloads caused ArcGIS to crash).

---

## Key takeaway (from the map)
Hospital access is generally strongest in central parts of the GTA, while some outer areas show longer drive times—important to consider where DA-level 65+ concentration is higher.

---

## Limitations
- Drive-time results depend on road network assumptions (no real-time traffic).
- Data is from 2016, so patterns may have changed since then.

---

## Files in this repository
- `Final map layout 2026.png` — final map layout
- `QGIS Day Presentation comp.pptx` — GIS Day 2025 presentation slides
- `README.md` — project documentation
