# Does Neural Network Architecture Affect Distillation Temperature? An Empirical Study

**Aaron Pacis · Allyana Coleen Reyes · Stacy Alyssa Uy**

*Ateneo de Manila University — Department of Mathematics*
*B.S. Applied Mathematics with Specialization in Data Science*
*April 24, 2026*

**[Read the full manuscript (PDF)](AMDSci_Undergraduate_Research_2025__Pacis__Reyes__Uy.pdf)**

**[View the experiment notebook (nbviewer)](https://nbviewer.org/github/honap1/Thesis-Knowledge-Distillation/blob/main/%5BTHESIS%5D%20Knowledge%20Distilation%20.ipynb)**

**[View the results notebook (nbviewer)](https://nbviewer.org/github/honap1/Thesis-Knowledge-Distillation/blob/main/ResultsGeneration.ipynb)**

---

## Repository Structure

```
├── [THESIS] Knowledge Distilation .ipynb                      # Main experiment notebook
├── ResultsGeneration.ipynb                                    # Results generation and analysis notebook
├── AMDSci_Undergraduate_Research_2025__Pacis__Reyes__Uy.pdf  # Full thesis manuscript
│
├── outputs/
│   ├── 2_Original_Dataset/                  # Raw Adult Income dataset (OpenML ID 1590)
│   ├── 3_Clean_Dataset/                     # Preprocessed dataset (imputed + label-encoded)
│   └── temperature_visualizations/          # Temperature scaling visualizations per model
│
├── kd_results_category_matched/
│   ├── kd_all_seeds_results.csv             # All 2,700 KD runs (category-matched)
│   ├── kd_best_configs_with_f1.csv          # Best config per teacher with F1/Recall
│   ├── category_summary.csv                 # Aggregated summary
│   ├── kd_category_matched_results_RERUN_REFERENCE.csv  # Rerun reference file
│   ├── kd_full_results_RERUN_REFERENCE.pkl              # Full rerun reference (pickle)
│   ├── seed_42/                             # Per-seed results (seed=42)
│   ├── seed_123/                            # Per-seed results (seed=123)
│   └── seed_456/                            # Per-seed results (seed=456)
│
└── kd_results_mismatch/
    ├── kd_mismatch_all_seeds.csv            # All 8,100 KD runs (heterogeneous mismatch)
    ├── kd_mismatch_best_configs_with_f1.csv # Best config per pair with F1/Recall
    ├── mismatch_summary.csv                 # Aggregated summary
    ├── sensitivity_scores.csv               # Temperature sensitivity analysis
    ├── kd_mismatch_results_RERUN_REFERENCE.csv  # Rerun reference file
    ├── kd_mismatch_full_RERUN_REFERENCE.pkl     # Full rerun reference (pickle)
    ├── seed_42/                             # Per-seed results (seed=42)
    ├── seed_123/                            # Per-seed results (seed=123)
    └── seed_456/                            # Per-seed results (seed=456)
```

## Dataset

- **Source:** UCI Adult Income (Census Income), OpenML ID 1590
- **Size:** 48,842 samples × 14 features + 1 target
- **Task:** Binary classification — predict whether income exceeds $50K/year
- **Split:** 70% train / 10% val / 20% test (stratified, seed=42)

## Models

**Teachers (9):** StandardMLP, RegularizedMLP, DeepMLP, AutoInt, FTTransformer, TabTransformer, DeepFM, WideAndDeep, DCN

**Students (3 per teacher):** StudentMLP, StudentAttention, StudentHybrid

## Experiments

1. **Temperature Scaling** — post-hoc calibration on all 9 teachers (5 seeds)
2. **Category-Matched KD** — student trained by same-category teacher (3 seeds × 100 (T, α) configs)
3. **Heterogeneous KD** — student trained by cross-category teacher (3 student types × 9 teachers × 100 configs)
