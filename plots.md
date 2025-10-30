---
layout: page
title: "AIS Heatmaps and Vessel Activity"
permalink: /plots/
---

# 🗺️ Comparative AIS Heatmaps — America's Cup vs Baseline

This section compares vessel activity in front of **Port Vell (Barcelona)** during the **37th America's Cup (October 2024)** and a **baseline day (July 2024)**, based on AIS vessel position data.  
The first panel below shows two screenshots of aggregated AIS activity with an interactive slider, while the second section contains interactive maps for each period.

---

<style>
.image-compare {
  --splitter-color: #0077b6;
  --splitter-size: 0.16rem;
  --expand: 0.9rem;
  --handle-size: calc(var(--expand) + var(--splitter-size));
  position: relative;
  max-width: 1000px;     /* set this near your PNG width */
  margin: 0 auto 1.5rem;
  background: #dbefff;
  border-radius: 12px;
  overflow: hidden;
  user-select: none;
}
.image-compare span {
  display: block;
  position: absolute;
  top: 0;
  left: calc(-1 * var(--expand));
  bottom: calc(-1 * var(--expand));
  width: calc(var(--expand) + 50% + var(--splitter-size)/2);
  max-width: calc(var(--expand) + 100%);
  min-width: var(--handle-size);
  padding-left: var(--expand);
  padding-bottom: var(--expand);
  background:
    linear-gradient(135deg, transparent 0, transparent 50%, var(--splitter-color) 50%, var(--splitter-color))
    100% 100% / var(--handle-size) var(--handle-size) no-repeat;
  resize: horizontal;   /* ← this is the trick: browser gives you the slider */
  overflow: hidden;
}
.image-compare img {
  display: block;
  width: 100%;
  height: auto;
  pointer-events: none;
}
.image-compare > img {
  max-width: 100%;
  height: auto;
}
.image-compare span::after {
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  bottom: var(--expand);
  border-right: var(--splitter-size) solid var(--splitter-color);
}

/* accessibility / keyboard fallback */
@keyframes img-pingpong {
  0%, 100% { width: calc(var(--expand) + 50% + var(--splitter-size)/2); }
  25%      { width: calc(var(--expand) + 100%); }
  75%      { width: var(--handle-size); }
}
.image-compare:focus span {
  animation: img-pingpong 5s linear infinite;
  resize: none;
}
</style>

## 🔹 Visual Comparison (baseline vs pre-race)

<figure style="text-align:center;">
  <figcaption style="margin-bottom:0.5rem;">
    <strong>Figure 1.</strong> AIS vessel density — baseline (18 July 2024, 12:00–14:00 UTC) vs pre-race (19 October 2024, 12:00–14:00 UTC).
    Drag the vertical bar to compare.
  </figcaption>

  <p class="image-compare" role="img" tabindex="0"
     aria-label="Interactive comparison of two AIS heatmaps for Barcelona">
    <!-- the draggable / resizable part -->
    <span>
      <!-- LEFT / FIRST image = baseline -->
      <img src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.png"
           alt="Baseline AIS heatmap (July 18, 2024)">
    </span>
    <!-- RIGHT / SECOND image = pre-race -->
    <img src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.png"
         alt="Pre-race AIS heatmap (Oct 19, 2024)">
  </p>
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
