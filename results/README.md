# Results

This directory contains all quantitative and qualitative results obtained from the
evaluation of the three segmentation models on the SEN12Landslide Hokkaido SAR subset:

- **Vanilla U-Net**
- **Attention U-Net**
- **Temporal U-Net with ConvLSTM bottleneck**

The results are organized into benchmark tables and visual figures for clarity
and reproducibility.

---

## Benchmarks

The `benchmarks/` subdirectory includes quantitative evaluation results computed
on the held-out test set using a fixed decision threshold of **0.5**.

### Files

- `benchmark_master.csv`  
  Consolidated comparison table summarizing all models, including Dice, Precision,
  Recall, F1-score, PR-AUC, and inference speed.

- `VanillaUNet_benchmark_thr0.5.csv`  
  Detailed per-metric results for the Vanilla U-Net model.

- `AttentionUNet_benchmark_thr0.5.csv`  
  Detailed per-metric results for the Attention U-Net model.

- `TemporalUNet_ConvLSTM_benchmark_thr0.5.csv`  
  Detailed per-metric results for the

  | Model | Dice | PR-AUC | Notes |
|------|------|--------|------|
| Vanilla U-Net | ... | ... | Baseline |
| Attention U-Net | ... | ... | Better localization |
| Temporal U-Net | ... | ... | Temporal noise sensitivity |

