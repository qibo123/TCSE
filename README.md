# TCSE: Time-aware Causal Disentanglement with Semantic Knowledge Enhancement for Personalized Mobile Application Recommendation
**TCSE** is a novel recommendation framework designed to effectively address time-varying popularity bias and semantic sparsity, particularly in mobile app ecosystems. By synergizing causal disentanglement with LLM-empowered semantic reasoning, TCSE accurately isolates genuine user interest from herd behavior driven by social conformity.


## Repository Layout

```
TCSE/
├── README.md
├── requirements.txt
├── configs/
│   └── tcse_example.yaml
├── scripts/
│   └── train_tcse.py
└── tcse/
    ├── __init__.py
    ├── data.py
    ├── metrics.py
    ├── model.py
    └── trainer.py
```

You can extend this tree with additional configs or notebooks as needed before pushing to GitHub.

## Quick Start

1. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
2. **Prepare data**
   Place your dataset under a directory that contains `train_record.csv`, `val_record.csv`, `test_record.csv`, and (optionally) `item_text_embeddings.npy`. Each CSV should have `uid,iid,ts` columns with zero-based IDs.
3. **Edit config**
   Copy `configs/tcse_example.yaml` and update the paths (`data_root`, `item_text_emb_path`, `output_dir`) plus hyper-parameters such as `int_weight`, `pop_weight`, `pop_margin`, and early-stopping controls (`monitor_metric`, `patience`).
4. **Train & evaluate**
   ```bash
   python scripts/train_tcse.py --config configs/tcse_example.yaml
   ```
   Training logs, checkpoints, and evaluation summaries are stored under the configured `output_dir`.

## Citation

If you use TCSE in academic work, please cite the accompanying paper once it is available. For now, referencing this repository is sufficient.
