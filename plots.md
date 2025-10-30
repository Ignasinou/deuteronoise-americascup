---
layout: page
title: "AIS Heatmaps and Vessel Activity"
permalink: /plots/
---

# 🗺️ Comparative AIS Heatmaps — America's Cup vs Baseline

This section compares vessel activity in front of **Port Vell (Barcelona)** during the **37th America's Cup (October 2024)** and a **baseline day (July 2024)**, based on AIS vessel position data.  
The first panel below shows two screenshots of aggregated AIS activity with an interactive slider, while the second section contains interactive maps for each period.

---

## 🔹 Visual Comparison (baseline vs pre-race)

<iframe
  src="{{ site.baseurl }}/plots/ais_compare.html"
  width="100%"
  height="720"
  style="border:none; border-radius:10px; overflow:hidden;"
  loading="lazy">
</iframe>

---

## 🔹 Interactive AIS Maps

<figure style="text-align:center;">
  <figcaption>
    <strong>Figure 2.</strong> Interactive AIS vessel trajectories during and before the America’s Cup event.  
    Each coloured trace represents a unique vessel path derived from the synchronised AIS dataset.
  </figcaption>

  <!-- During the America's Cup -->
  <h3 style="margin-top:1.5rem;">During the America’s Cup — 19 October 2024 (12:00–14:00 UTC)</h3>
  <iframe src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.html"
          width="100%" height="650" style="border:none; border-radius:10px; margin-bottom:2rem;"></iframe>

  <!-- Baseline (non-event) period -->
  <h3>Baseline Period — 18 July 2024 (12:00–14:00 UTC)</h3>
  <iframe src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.html"
          width="100%" height="650" style="border:none; border-radius:10px;"></iframe>
</figure>

---

### 🧭 Interpretation
During the America’s Cup period, vessel density increased sharply near the race perimeter and within Port Vell, with numerous spectator and support vessels visible.  
By contrast, the baseline period shows sparse, mostly linear port-approach traffic, characteristic of regular summer recreational activity.
---
