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
    <strong>Figure 1.</strong> Baseline (18 Jul 2024 12-14 UTC) vs Pre-race (19 Oct 2024 12-14 UTC).  
    Drag the white handle to reveal one map over the other.
  </figcaption>

  <style>
    #ba-wrap {
      position: relative;
      width: 1000px;   /* <-- fixed width of your PNGs */
      height: 600px;   /* <-- fixed height of your PNGs */
      margin: 1.5rem auto;
      overflow: hidden;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      background: #000;
      user-select: none;
    }
    #ba-base, #ba-top {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: cover;      /* keep aspect ratio, fill box */
      pointer-events: none;
    }
    #ba-clip {
      position: absolute;
      top: 0;
      left: 0;
      width: 50%;
      height: 100%;
      overflow: hidden;
    }
    #ba-slider {
      position: absolute;
      top: 0;
      left: 50%;
      width: 3px;
      height: 100%;
      background: #ffffff;
      cursor: ew-resize;
      z-index: 3;
    }
    #ba-handle {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%,-50%);
      width: 20px;
      height: 20px;
      background: #ffffff;
      border-radius: 50%;
      border: 2px solid #0077b6;
      box-shadow: 0 0 6px rgba(0,0,0,0.4);
    }
    .ba-label {
      position: absolute;
      top: 10px;
      padding: 4px 8px;
      background: rgba(255,255,255,0.8);
      border-radius: 4px;
      font-weight: 600;
      font-size: 0.9rem;
    }
    .ba-left { left: 10px; }
    .ba-right { right: 10px; }
  </style>

  <div id="ba-wrap">
    <img id="ba-base"
         src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.png"
         alt="Baseline AIS">

    <div id="ba-clip">
      <img id="ba-top"
           src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.png"
           alt="Pre-race AIS">
    </div>

    <div id="ba-slider"><div id="ba-handle"></div></div>
    <div class="ba-label ba-left">Baseline</div>
    <div class="ba-label ba-right">Pre-Race</div>
  </div>

  <script>
    document.addEventListener("DOMContentLoaded",function(){
      const wrap=document.getElementById("ba-wrap");
      const clip=document.getElementById("ba-clip");
      const slider=document.getElementById("ba-slider");
      let dragging=false;

      function move(x){
        const rect=wrap.getBoundingClientRect();
        let pos=x-rect.left;
        pos=Math.max(0,Math.min(pos,rect.width));
        clip.style.width=pos+"px";
        slider.style.left=pos+"px";
      }

      const start=e=>{dragging=true;e.preventDefault();};
      const stop=()=>dragging=false;
      const drag=e=>{
        if(!dragging)return;
        move(e.touches?e.touches[0].clientX:e.clientX);
      };

      slider.addEventListener("mousedown",start);
      window.addEventListener("mouseup",stop);
      window.addEventListener("mousemove",drag);
      slider.addEventListener("touchstart",start);
      window.addEventListener("touchend",stop);
      window.addEventListener("touchmove",drag);
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
