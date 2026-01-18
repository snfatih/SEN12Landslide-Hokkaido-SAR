# SEN12Landslide-Hokkaido-SAR

## Overview

This repository presents a comparative study on landslide segmentation using Synthetic Aperture Radar (SAR) data based on the SEN12Landslide dataset, with a focus on the Hokkaido subset corresponding to the 2018 Eastern Iburi Earthquake.
The project evaluates the performance of three deep learning architectures for pixel-wise landslide detection under severe class imbalance conditions.

The study emphasizes segmentation accuracy, robustness, and the impact of attention mechanisms and temporal modeling, with relevance for rapid disaster response scenarios.

## Dataset

We use the SEN12Landslide dataset introduced by Höhn et al., which combines multi-modal and multi-temporal satellite observations with pixel-level landslide annotations.

- **Region:** Hokkaido, Japan  
- **Event:** 2018 Eastern Iburi Earthquake  
- **Input data:** Sentinel-1 SAR image time series  
- **Labels:** Binary landslide masks  
- **Data format:** NetCDF (.nc)

Due to the strong class imbalance and heterogeneous terrain, this subset is particularly suitable for evaluating SAR-based landslide segmentation methods.

## Evaluated Models

The following architectures are implemented and benchmarked:

- **Vanilla U-Net**
- **Attention U-Net**
- **Temporal U-Net with ConvLSTM bottleneck**

All models are trained and evaluated using the same train/validation/test split to ensure a fair and controlled comparison.

## Repository Structure

```text
SEN12Landslide-Hokkaido-SAR/
├── data/            # Dataset access notes and placeholders
├── notebooks/       # Jupyter notebooks for preprocessing and training
├── src/             # (Planned) modular implementation of models and training pipeline
├── results/
│   ├── Figures/     # Training curves, PR curves, confusion matrices, qualitative examples
│   │   ├── VanillaUNet/
│   │   ├── AttentionUNet/
│   │   └── TemporalUNet_ConvLSTM/
│   ├── benchmarks/  # Quantitative results (CSV / JSON)
│   └── README.md
└── README.md        # Project overview
```
## Results

Quantitative and qualitative results are provided in the `results/` directory.

### Quantitative Evaluation

The evaluation focuses on:

- Dice coefficient  
- Precision–Recall (PR) AUC  
- Precision and Recall at a fixed threshold of 0.5  

Benchmark results are available as:

- Per-model CSV and JSON files  
- A consolidated `benchmark_master.csv` for cross-model comparison  

### Qualitative Evaluation

- Visual comparison of predicted landslide masks  
- Selected examples highlighting false positives and false negatives  

See `results/Figures/` and `results/README.md` for details.


Reproducibility

All experiments were conducted using fixed random seeds and identical dataset splits.
Exact model configurations, thresholds, and evaluation settings are stored in the benchmark files to facilitate reproducibility.
## References

1. Höhn, P., Zöllner, M., d’Angelo, P., & Wegner, J. D. (2022).  
   **SEN12Landslide: A Benchmark Dataset for Landslide Detection from Multi-Modal Satellite Data**.  
   *IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing (JSTARS)*.  
   Dataset and code: https://github.com/PaulH97/Sen12Landslides

2. Nava, L., Giannetti, F., and Moretti, S. (2021).  
   **Deep Learning for Rapid Landslide Detection Using Synthetic Aperture Radar (SAR) Data**.  
   *Remote Sensing*, 13(16), 3270.  
   https://doi.org/10.3390/rs13163270

3. Boehm, J., d’Angelo, P., & Wegner, J. D. (2022).  
   **Deep Learning for Rapid Landslide Detection Using SAR Datacubes**.  
   *ISPRS Annals of the Photogrammetry, Remote Sensing and Spatial Information Sciences*.  

