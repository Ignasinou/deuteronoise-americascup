---
layout: page
title: "Data Access"
permalink: /data/
---

# DeuteroNoise Dataset — America's Cup (Barcelona, 2024)

The data presented in this project form part of the **DeuteroNoise Dataset**, an open, calibrated, multi-basin corpus that combines **underwater acoustic recordings** with **Automatic Identification System (AIS)** vessel data.  
This dataset provides time-synchronised information to quantify the acoustic footprint of maritime traffic in coastal environments.

---

## Dataset DOI
*To be updated once the Zenodo DOI is available.*  
(Preliminary dataset available through the [DeuteroNoise GitHub repository](https://github.com/Ignasinou/deuteronoise-dataset-preview).)

---

## Deployment Metadata
- **Hydrophone:** Aquarian Audio AS-1 (–209.7 dB re 1 V/µPa nominal sensitivity)  
- **Recorder:** uRec-384k (Nauta-RCS, Italy), 48 kHz / 24-bit continuous recording  
- **Depth:** approximately 20 m (sensor positioned 1 m above seabed)  
- **Location:** Espai Vela, Port Vell, Barcelona, Spain  
- **Coordinates:** 41.371° N, 2.195° E (WGS 84)  
- **Campaign periods:** March–July 2024 (baseline) and October 2024 (America’s Cup event)

---

## Access and Tools
The dataset will be distributed through:
- A **RESTful API** for programmatic data access (JSON format)  
- An **interactive dashboard** for exploring time-series and spectral metrics (developed in *FastAPI + Streamlit*)  
- Archived data packages (CSV + WAV subsets) hosted on **Zenodo**

Detailed technical documentation and usage examples are available at the  
[DeuteroNoise GitHub repository](https://github.com/Ignasinou/deuteronoise-dataset-preview).

---

## Citation
If you use this, please cite:

> Nou-Plana, I., Alsina-Pagès, R.M., *et al.* (2025). **Underwater soundscape during the 37th America’s Cup (Barcelona, 2024): Quantifying event-related vessel noise from the DeuteroNoise Dataset**  

---

## Related Resources
- [Interactive acoustic visualizations](plots.md)  