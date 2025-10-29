## 🔹 Visual Comparison (Screenshots with Slider)

<figure style="text-align:center;">
  <figcaption>
    <strong>Figure 1.</strong> Comparison of AIS vessel density between a baseline day
    (18 July 2024, 12:00–14:00 UTC) and a pre-race period
    (19 October 2024, 12:00–14:00 UTC).  
    Use the slider to reveal differences in spatial vessel activity around Port Vell and the race perimeter.
  </figcaption>

  <style>
  .img-compare-container {
    position: relative;
    width: 100%;
    max-width: 1000px;
    margin: 1.5rem auto;
    overflow: hidden;
    border-radius: 10px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }
  .img-compare-container img {
    display: block;
    width: 100%;
    height: auto;
    user-select: none;
    pointer-events: none;
  }
  .img-compare-overlay {
    position: absolute;
    top: 0;
    left: 0;
    overflow: hidden;
    width: 50%; /* initial slider position */
  }
  .img-compare-slider {
    position: absolute;
    z-index: 10;
    top: 0;
    left: 50%;
    transform: translateX(-50%);
    width: 4px;
    height: 100%;
    background: #0077b6;
    cursor: ew-resize;
  }
  </style>

  <div class="img-compare-container" id="compareContainer">
    <img src="{{ site.baseurl }}/plots/heatmap_A_baseline_20240718_1200_1400.png" alt="Baseline AIS Heatmap">
    <div class="img-compare-overlay" id="compareOverlay">
      <img src="{{ site.baseurl }}/plots/heatmap_B_prerace_20241019_1200_1400.png" alt="Pre-race AIS Heatmap">
    </div>
    <div class="img-compare-slider" id="compareSlider"></div>
  </div>

  <script>
  document.addEventListener("DOMContentLoaded", function() {
    const container = document.getElementById("compareContainer");
    const overlay = document.getElementById("compareOverlay");
    const slider = document.getElementById("compareSlider");
    let isDragging = false;

    const moveSlider = (x) => {
      const rect = container.getBoundingClientRect();
      let pos = x - rect.left;
      pos = Math.max(0, Math.min(pos, rect.width));
      overlay.style.width = pos + "px";
      slider.style.left = pos + "px";
    };

    slider.addEventListener("mousedown", () => isDragging = true);
    window.addEventListener("mouseup", () => isDragging = false);
    window.addEventListener("mousemove", (e) => {
      if (isDragging) moveSlider(e.clientX);
    });

    // for touch devices
    slider.addEventListener("touchstart", () => isDragging = true);
    window.addEventListener("touchend", () => isDragging = false);
    window.addEventListener("touchmove", (e) => {
      if (isDragging && e.touches.length) moveSlider(e.touches[0].clientX);
    });
  });
  </script>
</figure>