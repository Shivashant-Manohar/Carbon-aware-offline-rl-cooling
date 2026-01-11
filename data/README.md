# Data Directory

This directory contains the **raw and processed datasets** used for training and evaluating the
carbon-aware offline reinforcement learning models for data center cooling.

All learning is performed in a **strictly offline setting**, using historical operational data only.

---

## Directory Structure

```text
data/
├── raw/
│   ├── hvac_logs.csv
│   └── carbon_intensity.csv
│
├── processed/
│   ├── offline_dataset.pkl
│   └── stats.json
│
└── README.md
