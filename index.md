# DeuteroNoise – America's Cup Soundscapes 🌊

This project explores the **underwater acoustic footprint of the 37th America’s Cup in Barcelona (2024)**, using calibrated hydrophone recordings and AIS data from the [**DeuteroNoise Dataset**](https://github.com/Ignasinou/deuteronoise-dataset-preview).

![Espai Vela Hydrophone Setup](/assets/espai_vela.png)

---

## 🎯 Project Overview

Between March and October 2024, continuous underwater sound recordings were collected near **Port Vell (Espai Vela)**, coinciding with the final competition weeks of the 37th America’s Cup.

By comparing these data with **non-event baselines** (March and July 2024), we quantified how vessel activity during the regatta altered the coastal soundscape.

Key findings:
- Broadband SPL increased by **up to 20 dB re 1 µPa rms** during race days  
- Diurnal noise cycles flattened (continuous high noise even at night)  
- Low-frequency bands (63 Hz and 125 Hz) dominated by propulsion noise  

See [Results and Interactive Plots](plots.md) for details.

---

## 🔍 Data Access

All raw and processed data belong to the **DeuteroNoise Dataset**, an open, calibrated, multi-basin database pairing hydrophone recordings with AIS data.

- 📦 Dataset DOI: [Zenodo link (to be added)]()
- 🧭 API Access: [FastAPI endpoint (if online)]()
- 🧾 Metadata: campaign tables, vessel types, and calibration constants

---

## 🧑‍🔬 References
- Nou-Plana, I. & Alsina-Pagés, R.M. (2026). *37th America’s Cup in Barcelona: Quantifying noise pollution impacts on underwater soundscapes from the DeuteroNoise Dataset.* ICASSP 2026.
- Pine, M.K. et al. (2024). *Not so silent spectators: How spectator vessels at international sailing regattas alter marine soundscapes.* *Marine Pollution Bulletin*, 202, 116309.
- Nou-Plana, I. et al. (2025). *The DeuteroNoise Dataset: An open, calibrated, multi-basin resource for vessel noise and natural soundscapes.* *Applied Acoustics*.

---
> This website is maintained by the Human-Environment Research group (HER), La Salle – Universitat Ramon Llull.