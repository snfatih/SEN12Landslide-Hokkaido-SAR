# Results

This directory contains all quantitative and qualitative results obtained from the
evaluation of the three segmentation models on the SEN12Landslide Hokkaido SAR subset:

- **Vanilla U-Net**
- **Attention U-Net**
- **Temporal U-Net with ConvLSTM bottleneck**

The results are organized into benchmark tables and visual figures for clarity
and reproducibility.

---

# Benchmarks

The `benchmarks/` subdirectory contains quantitative evaluation results computed on the held-out
test set using a fixed decision threshold of **0.5**.

All models are evaluated using identical test data and metrics to ensure a fair comparison.

---

## Files

- `benchmark_master.csv`  
  Consolidated comparison table summarizing all evaluated models, including:
  Dice coefficient, Precision, Recall, F1-score, PR-AUC, and inference speed.

- `VanillaUNet_benchmark_thr0.5.csv`  
  Detailed per-metric evaluation results for the **Vanilla U-Net** model.

- `AttentionUNet_benchmark_thr0.5.csv`  
  Detailed per-metric evaluation results for the **Attention U-Net** model.

- `TemporalUNet_ConvLSTM_benchmark_thr0.5.csv`  
  Detailed per-metric evaluation results for the **Temporal U-Net with ConvLSTM bottleneck** model.

---

## Summary (Qualitative Interpretation)

## Quantitative Summary (Threshold = 0.5)

The table below reports the quantitative performance of all evaluated models on the held-out
test set using a fixed decision threshold of **0.5**.

| Model                     | Precision | Recall | F1 / Dice | IoU  | Accuracy | Inference Time (s/sample) |
|---------------------------|-----------|--------|-----------|------|----------|----------------------------|
| Vanilla U-Net             | 0.51      | 0.61   | 0.56      | 0.39 | 0.93     | **1.61** |
| Attention U-Net           | **0.52**  | 0.61   | **0.56**  | **0.39** | 0.93 | 1.76 |
| Temporal U-Net (ConvLSTM) | 0.49      | 0.39   | 0.43      | 0.28 | 0.93     | 2.18 |

### Interpretation

- The **Attention U-Net** slightly outperforms the Vanilla U-Net in terms of Precision and IoU,
  indicating improved spatial localization due to attention mechanisms.
- The **Temporal U-Net (ConvLSTM)** shows lower overall performance, likely due to sensitivity
  to temporal noise and limited temporal context in the SAR time series.
- The **Vanilla U-Net** provides a strong baseline with the fastest inference time, making it
  suitable for time-critical disaster response scenarios.

