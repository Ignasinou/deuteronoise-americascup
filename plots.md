---
layout: page
title: "AIS Heatmaps and Vessel Activity"
permalink: /plots/
---

# Comparative AIS Heatmaps — America's Cup vs. Baseline

This section compares vessel activity in front of **Port Vell (Barcelona)** during the **37th America’s Cup (October 2024)** and a **baseline day (July 2024)**, using Automatic Identification System (AIS) vessel-position data from the [DeuteroNoise Dataset](https://github.com/Ignasinou/deuteronoise-dataset-preview).  
The maps illustrate how vessel density and movement patterns changed around the Espai Vela hydrophone site.

---

## Visual Comparison (Baseline vs. Pre-Race)

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

## Interactive AIS Maps

<figure style="text-align:center;">
  <figcaption>
    <strong>Figure 2.</strong> Interactive AIS vessel trajectories recorded before and during the America’s Cup event.  
    Each coloured trace corresponds to a unique vessel path reconstructed from the time-synchronised DeuteroNoise AIS dataset.
  </figcaption>

  <h3 style="margin-top:1.5rem;">During the America’s Cup — 19 October 2024 (12:00–14:00 UTC)</h3>
  <iframe src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.html"
          width="100%" height="650" style="border:none; border-radius:10px; margin-bottom:2rem;"></iframe>

  <h3>Baseline Period — 18 July 2024 (12:00–14:00 UTC)</h3>
  <iframe src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.html"
          width="100%" height="650" style="border:none; border-radius:10px;"></iframe>
</figure>

---

## Interpretation
During the **America’s Cup period**, vessel density and traffic intensity increased near the race perimeter and along the main port-entrance channel, with clusters of support, security, and spectator boats visible around the Espai Vela hydrophone.  
In contrast, the **baseline period** shows moderate, mostly linear port-approach traffic typical of normal summer operations.  
These spatial patterns correspond closely to the acoustic observations, where broadband SPLs increased by approximately **5–8 dB re 1 µPa**, and the natural **day–night cycle** flattened during the event, reflecting continuous vessel activity associated with race operations.