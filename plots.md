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
  <figcaption>
    <strong>Figure 1.</strong> Baseline (18 Jul 2024 12–14 UTC) vs Pre-race (19 Oct 2024 12–14 UTC).  
    Drag the white bar to compare the two AIS heatmaps.
  </figcaption>

  <style>
    * {box-sizing:border-box;}
    .img-comp-container {
      position: relative;
      max-width: 1000px;
      margin: 1.5rem auto;
      overflow: hidden;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    .img-comp-img {
      position: absolute;
      width: 100%;
      height: auto;
      overflow: hidden;
    }
    .img-comp-img img {
      display: block;
      width: 100%;
      height: auto;
      vertical-align: middle;
    }
    .img-comp-slider {
      position: absolute;
      z-index: 9;
      cursor: ew-resize;
      width: 3px;
      height: 100%;
      background-color: #ffffff;
      opacity: 0.9;
      top: 0;
      left: 50%;
    }
    .slider-handle {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 22px;
      height: 22px;
      background: #ffffff;
      border-radius: 50%;
      border: 2px solid #0077b6;
      box-shadow: 0 0 6px rgba(0,0,0,0.3);
    }
    .ba-label {
      position: absolute;
      top: 10px;
      background: rgba(255,255,255,0.8);
      padding: 4px 8px;
      border-radius: 4px;
      font-weight: 600;
      font-size: 0.9rem;
    }
    .ba-left { left: 10px; }
    .ba-right { right: 10px; }
  </style>

  <div class="img-comp-container" id="compContainer">
    <!-- Bottom (baseline) image -->
    <div class="img-comp-img">
      <img src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.png" alt="Baseline AIS Heatmap">
    </div>

    <!-- Top (overlay) image -->
    <div class="img-comp-img img-comp-overlay" id="overlayImg">
      <img src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.png" alt="Pre-race AIS Heatmap">
    </div>

    <!-- Slider + handle -->
    <div class="img-comp-slider" id="compSlider">
      <div class="slider-handle"></div>
    </div>

    <div class="ba-label ba-left">Baseline</div>
    <div class="ba-label ba-right">Pre-Race</div>
  </div>

  <script>
    // ---- exact logic from W3Schools ----
    document.addEventListener("DOMContentLoaded",function(){
      const overlay=document.getElementById("overlayImg");
      const slider=document.getElementById("compSlider");
      const container=document.getElementById("compContainer");
      let clicked=false;

      // set overlay width & slider position to middle
      function init() {
        const w=container.offsetWidth;
        overlay.style.width=(w/2)+"px";
        slider.style.left=(w/2)+"px";
      }
      init(); // initial placement
      window.addEventListener("resize",init); // maintain on resize

      function slide(x){
        const rect=container.getBoundingClientRect();
        let pos=x-rect.left;
        if(pos<0)pos=0;
        if(pos>rect.width)pos=rect.width;
        overlay.style.width=pos+"px";
        slider.style.left=pos+"px";
      }

      const start=e=>{e.preventDefault();clicked=true;};
      const stop=()=>clicked=false;
      const move=e=>{
        if(!clicked)return;
        slide(e.touches?e.touches[0].clientX:e.clientX);
      };

      slider.addEventListener("mousedown",start);
      window.addEventListener("mouseup",stop);
      window.addEventListener("mousemove",move);
      slider.addEventListener("touchstart",start);
      window.addEventListener("touchend",stop);
      window.addEventListener("touchmove",move);
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
