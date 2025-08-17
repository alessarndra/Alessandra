---
title: "Research"
permalink: /research/
layout: single
author_profile: true
toc: true
toc_sticky: true
classes: wide
---

<div class="mm-card">
  <p>This page highlights four substantive research experiences. I’m keeping full undergraduate reports private and presenting concise, professional summaries. If you’d like more detail on any project, please <a href="/contact/">get in touch</a>.</p>
</div>

## Photoprotective Proteins in Plants – Final-Year Project (Cambridge)

**Affiliation:** Kromdijk Group, Dept. of Plant Sciences, University of Cambridge  
**Focus:** Functional diversity of early-diverging <strong>PsbS</strong> proteins and their role in NPQ dynamics under fluctuating light  
**Approach:** Chlorophyll fluorescence assays, qPCR gene profiling, protein sequence modelling, R/Python analysis  
**Insights:** Variation in photoprotective capacity across PsbS homologues that may inform future crop light-use efficiency work.

---

## Critical Review: “Ecosystem Health” Concepts

**Scope:** Compared biodiversity metrics (taxonomic & functional), resilience/stability lenses, and ecosystem-services valuation to examine how “ecosystem health” is conceptualised in conservation.  
**Conclusion:** Best treated as a context-specific, multi-metric construct rather than a single index; clarity of definition matters for policy and practice.

---

## Leaf-Trapping Fungi & Forest Ecology (Borneo: Danum Valley Field Centre)

<div class="mm-card" style="padding:0;">
  <div id="map-danum" class="leaflet-map" aria-label="Map: Danum Valley Field Centre, Sabah, Borneo"></div>
</div>

**Context:** Sabah’s lowland dipterocarp forest (DVFC), a leading biodiversity research hub.  
**Focus:** Abundance & ecological implications of aerial leaf-catching fungal networks (Masiminius spp.) in logged vs. primary forest.  
**Techniques:** Canopy surveys, photosynthetic measurements, ImageJ image analysis, R statistics.  
**Take-home:** Fungal nets were <em>more prevalent in disturbed/logged</em> areas and supported arthropod microhabitats; no clear photosynthesis effect in this small-scale study.

---

## Behavioural Ecology of Damaraland Mole-Rats (Kalahari, South Africa)

<div class="mm-card" style="padding:0;">
  <div id="map-kuruman" class="leaflet-map" aria-label="Map: Kuruman River Reserve, Kalahari"></div>
</div>

**Supervisor:** Prof. Tim Clutton-Brock (Large Mammal Research Group, University of Cambridge) at **Kuruman River Reserve**  
**Focus:** Social structure, activity patterns, and cooperative behaviour in Damaraland mole-rats  
**Methods:** Field observations & focal sampling; R data analysis  
**Key insights:** Flexible division of labour consistent with energetic constraints and cooperative breeding; contributed notes to the long-term dataset.

---

### Skills Summary

- **Field ecology:** behavioural sampling, tropical forest surveys, canopy methods  
- **Analysis tools:** R, Python, ImageJ; data cleaning, visualisation, exploratory stats  
- **Lab:** chlorophyll fluorescence assays, qPCR basics, sequence/comparative modelling  
- **Professional:** scientific writing for mixed audiences, ethics & good field practice, planning in remote settings

<!-- ===== MAP SCRIPT ===== -->
<script>
// Danum Valley Field Centre (approx DVFC coords)
// Source: DVFC/academic sources list DVFC near ~5.017 N, 117.813 E
const danumLatLng = [5.017, 117.813];

// Kuruman River Reserve near Van Zylsrus, Northern Cape (approx site area)
// The reserve is commonly described near Van Zylsrus (~-26.878, 22.050)
const kurumanLatLng = [-26.878, 22.050];

// Shared tile layer
function tileLayer() {
  return L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '&copy; OpenStreetMap contributors'
  });
}

// Danum map
const mapDanum = L.map('map-danum', { scrollWheelZoom: false }).setView(danumLatLng, 11);
tileLayer().addTo(mapDanum);
L.marker(danumLatLng).addTo(mapDanum)
  .bindPopup('<strong>Danum Valley Field Centre</strong><br>Sabah, Malaysian Borneo')
  .openPopup();

// Kuruman map
const mapKuruman = L.map('map-kuruman', { scrollWheelZoom: false }).setView(kurumanLatLng, 10);
tileLayer().addTo(mapKuruman);
L.marker(kurumanLatLng).addTo(mapKuruman)
  .bindPopup('<strong>Kuruman River Reserve</strong><br>Northern Cape, South Africa (near Van Zylsrus)');

</script>
