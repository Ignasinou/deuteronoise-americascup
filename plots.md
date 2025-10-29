---
layout: page
title: "AIS Heatmaps and Vessel Activity"
permalink: /plots/
---

# 🗺️ Comparative AIS Heatmaps — America's Cup vs Baseline

This section compares vessel activity in front of **Port Vell (Barcelona)** during the **37th America's Cup (October 2024)** and a **baseline day (July 2024)**, based on AIS vessel position data.  
The first panel below shows two screenshots of aggregated AIS activity with an interactive slider, while the second section contains interactive maps for each period.

---

---
layout: page
title: "AIS Heatmaps and Vessel Activity"
permalink: /plots/
---

# 🗺️ Comparative AIS Heatmaps — America's Cup vs Baseline

This section compares vessel activity in front of **Port Vell (Barcelona)** during the **37th America's Cup (October 2024)** and a **baseline day (July 2024)**, based on AIS vessel position data.  
The first panel below shows two screenshots of aggregated AIS activity with an interactive slider, while the second section contains interactive maps for each period.

---

## 🔹 Visual Comparison

<figure style="text-align:center;">
  <figcaption style="margin-bottom:0.5rem;">
    <strong>Figure 1.</strong> Comparison of AIS vessel density between a baseline day
    (18 July 2024, 12:00–14:00 UTC) and a pre-race period
    (19 October 2024, 12:00–14:00 UTC).  
    Drag the slider to compare spatial vessel activity around Port Vell and the race perimeter.
  </figcaption>

  <style>
  .compare-container {
    position: relative;
    max-width: 1000px;
    margin: 1.5rem auto;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    user-select: none;
  }
  .compare-container img {
    display: block;
    width: 100%;
    height: auto;
    pointer-events: none;
  }
  .compare-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 50%; /* Start at midpoint */
    height: 100%;
    overflow: hidden;
  }
  .compare-overlay img {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: auto;
  }
  .compare-slider {
    position: absolute;
    z-index: 2;
    top: 0;
    left: 50%;
    width: 4px;
    height: 100%;
    background: #0077b6;
    cursor: ew-resize;
  }
  .compare-handle {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 20px;
    height: 20px;
    background: #0077b6;
    border: 3px solid white;
    border-radius: 50%;
    box-shadow: 0 0 6px rgba(0,0,0,0.3);
  }
  .label-left, .label-right {
    position: absolute;
    top: 10px;
    background: rgba(255,255,255,0.8);
    padding: 4px 8px;
    border-radius: 4px;
    font-weight: 600;
    font-size: 0.9rem;
  }
  .label-left { left: 10px; }
  .label-right { right: 10px; }
  </style>

  <div class="compare-container" id="compareContainer">
    <img src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.png" alt="Baseline AIS Heatmap">
    <div class="compare-overlay" id="compareOverlay">
      <img src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.png" alt="Pre-race AIS Heatmap">
    </div>
    <div class="compare-slider" id="compareSlider">
      <div class="compare-handle"></div>
    </div>
    <div class="label-left">Baseline</div>
    <div class="label-right">Pre-Race</div>
  </div>

  <script>
  document.addEventListener("DOMContentLoaded", function() {
    const container = document.getElementById("compareContainer");
    const overlay = document.getElementById("compareOverlay");
    const slider = document.getElementById("compareSlider");
    let isDragging = false;

    function moveSlider(x) {
      const rect = container.getBoundingClientRect();
      let pos = x - rect.left;
      pos = Math.max(0, Math.min(pos, rect.width));
      overlay.style.width = pos + "px";
      slider.style.left = pos + "px";
    }

    const startDrag = e => { e.preventDefault(); isDragging = true; };
    const stopDrag = () => (isDragging = false);
    const onDrag = e => {
      if (!isDragging) return;
      moveSlider(e.touches ? e.touches[0].clientX : e.clientX);
    };

    slider.addEventListener("mousedown", startDrag);
    window.addEventListener("mouseup", stopDrag);
    window.addEventListener("mousemove", onDrag);
    slider.addEventListener("touchstart", startDrag);
    window.addEventListener("touchend", stopDrag);
    window.addEventListener("touchmove", onDrag);
  });
  </script>
</figure>

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