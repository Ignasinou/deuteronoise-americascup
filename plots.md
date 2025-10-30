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

<div style="display:flex; flex-wrap:wrap; justify-content:center; gap:10px; margin-top:1rem;">
  <figure style="flex:1 1 480px; text-align:center;">
    <img src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.png"
         alt="Baseline AIS Heatmap"
         style="width:100%; height:auto; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.1);" />
    <figcaption style="margin-top:0.5rem; font-size:0.9rem; color:#333;">
      <strong>Baseline</strong> — 18 July 2024 (12:00–14:00 UTC)
    </figcaption>
  </figure>

  <figure style="flex:1 1 480px; text-align:center;">
    <img src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.png"
         alt="Pre-race AIS Heatmap"
         style="width:100%; height:auto; border-radius:10px; box-shadow:0 2px 8px rgba(0,0,0,0.1);" />
    <figcaption style="margin-top:0.5rem; font-size:0.9rem; color:#333;">
      <strong>Pre-race</strong> — 19 October 2024 (12:00–14:00 UTC)
    </figcaption>
  </figure>
</div>

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
