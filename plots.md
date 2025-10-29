---
layout: page
title: "AIS Heatmaps and Vessel Activity"
permalink: /plots/
---

# 🗺️ Comparative AIS Heatmaps — America's Cup vs Baseline

This section compares vessel activity in front of **Port Vell (Barcelona)** during the **37th America's Cup (October 2024)** and a **baseline day (July 2024)**, based on AIS vessel position data.  
The upper panel shows two screenshots of aggregated AIS activity with a slider overlay, and the lower panel provides fully interactive maps for detailed exploration.

---

## 🔹 Visual Comparison (Screenshots with Slider)

<figure style="text-align:center;">
  <figcaption>
    <strong>Figure 1.</strong> Comparison of AIS vessel density between a baseline day (18 July 2024, 12:00–14:00 UTC) and a pre-race period (19 October 2024, 12:00–14:00 UTC).  
    Use the slider to reveal differences in spatial vessel activity around Port Vell and the race perimeter.
  </figcaption>

  <div class="img-comp-container" id="imgCompContainer"
       style="position:relative; height:600px; max-width:1000px; margin:auto; overflow:hidden;">
    <img src="/plots/heatmap_A_baseline_20240718_1200_1400.png"
         style="position:absolute; width:100%; height:auto;" />
    <img src="/plots/heatmap_B_prerace_20241019_1200_1400.png"
         style="position:absolute; width:100%; height:auto; clip:rect(0,500px,600px,0);" id="topImage"/>
    <div id="slider"
         style="position:absolute; z-index:9; cursor:ew-resize; width:40px; height:100%;
                background-color:rgba(255,255,255,0.5); border-left:3px solid #0077b6;"></div>
  </div>
</figure>

<script>
// simple interactive image comparison slider
const slider = document.getElementById("slider");
const container = document.getElementById("imgCompContainer");
const topImage = document.getElementById("topImage");
let clicked = false;

slider.addEventListener("mousedown", () => clicked = true);
window.addEventListener("mouseup", () => clicked = false);
window.addEventListener("mousemove", e => {
  if (!clicked) return;
  const rect = container.getBoundingClientRect();
  let x = e.clientX - rect.left;
  x = Math.max(0, Math.min(x, rect.width));
  slider.style.left = `${x}px`;
  topImage.style.clip = `rect(0, ${x}px, ${rect.height}px, 0)`;
});
</script>

---

## 🔹 Interactive AIS Maps

<figure style="text-align:center;">
  <figcaption>
    <strong>Figure 2.</strong> Interactive AIS vessel trajectories during (left) and before (right) the America’s Cup event.  
    Pan, zoom, or hover to inspect vessel names and paths.
  </figcaption>

  <div style="display:flex; flex-wrap:wrap; justify-content:center; gap:10px;">
    <iframe src="/plots/heatmap_B_prerace_20241019_1200_1400.html"
            width="49%" height="650" style="border:none; border-radius:10px;"></iframe>
    <iframe src="/plots/heatmap_A_baseline_20240718_1200_1400.html"
            width="49%" height="650" style="border:none; border-radius:10px;"></iframe>
  </div>
</figure>

---

### 🧭 Interpretation
During the America’s Cup pre-race period, vessel density increased sharply near the race perimeter and within Port Vell, with numerous support and spectator vessels visible.  
By contrast, the baseline period shows sparse, mostly linear port-approach traffic, typical of regular summer recreational activity.