## SEN12Landslide-Hokkaido-SAR
## Overview

This repository presents a comparative study on landslide segmentation using Synthetic Aperture Radar (SAR) data based on the SEN12Landslide dataset, focusing on the Hokkaido (2018 Eastern Iburi Earthquake) subset.
The project evaluates the performance of three deep learning architectures for pixel-wise landslide detection under severe class imbalance conditions.

The study emphasizes model accuracy, robustness, and the impact of attention and temporal modeling for rapid disaster response scenarios.

## Dataset

We use the SEN12Landslide dataset introduced by Paul et al., which combines multi-modal and multi-temporal satellite observations with pixel-level landslide annotations.

Subset: Hokkaido, Japan

Event: 2018 Eastern Iburi Earthquake

Input data: Sentinel-1 SAR image time series

Labels: Binary landslide masks

Data format: NetCDF (.nc)

Due to the strong class imbalance and heterogeneous terrain, this subset is particularly suitable for evaluating SAR-based landslide segmentation methods.

## Evaluated Models

The following architectures are implemented and benchmarked:

Vanilla U-Net

Attention U-Net

Temporal U-Net with ConvLSTM bottleneck

All models are trained and evaluated on the same train/validation/test split to ensure a fair comparison.

## Repository Structure

```text
SEN12Landslide-Hokkaido-SAR/
│
├── data/               # Dataset access notes and placeholders
├── notebooks/          # Jupyter notebooks for preprocessing and training
│
├── src/                # (Planned) modular training and model code
│
├── results/
│   ├── Figures/        # Training curves, PR curves, confusion matrices
│   ├── benchmarks/     # Quantitative results (CSV / JSON)
│   └── README.md
│
└── README.md            # Project overview
```

## Results

Quantitative and qualitative results are provided in the results/ directory.

Quantitative Evaluation

Dice coefficient

Precision–Recall (PR) AUC

Precision and Recall at threshold 0.5

Benchmark results are available as:

Per-model CSV and JSON files

A consolidated benchmark_master.csv

Qualitative Evaluation

Visual comparison of predicted landslide masks

Selected examples highlighting false positives and false negatives

See results/Figures/ and results/README.md for details.

Reproducibility

All experiments were conducted using fixed random seeds and identical dataset splits.
Exact model configurations, thresholds, and evaluation settings are stored in the benchmark files.

## References

1. Höhn, P., Zöllner, M., d’Angelo, P., & Wegner, J. D.  
   **SEN12Landslide: A Benchmark Dataset for Landslide Detection from Multi-Modal Satellite Data**.  
   IEEE Journal of Selected Topics in Applied Earth Observations and Remote Sensing (JSTARS), 2022.  
   Dataset and code available at: https://github.com/PaulH97/Sen12Landslides

2. Boehm, J., Nava, L., Tasser, E., & Pfeifer, N.  
   **Deep Learning for Rapid Landslide Detection Using Synthetic Aperture Radar (SAR) Datacubes**.  
   ISPRS Journal of Photogrammetry and Remote Sensing, 2022.

3. Nava, L., Boehm, J., & Pfeifer, N.  
   **Operational Landslide Mapping from Multi-Temporal Sentinel-1 SAR Data Using Deep Learning**.  
   Remote Sensing, 2021.
