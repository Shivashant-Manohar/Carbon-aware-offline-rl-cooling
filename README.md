```markdown
# Carbon-Aware Offline Reinforcement Learning for Data Center Cooling

## Overview
Data centers are critical infrastructure for modern computing, yet their cooling systems consume nearly **30–40% of total data center energy**. Optimizing cooling efficiency is therefore one of the most impactful levers for reducing operational costs and environmental impact.

Recent research has shown that **Offline Reinforcement Learning (Offline RL)** can safely optimize data center cooling using only historical operational data, avoiding the risks of online exploration. However, existing approaches primarily optimize for **energy consumption alone**, ignoring the fact that **electricity carbon intensity varies over time**.

This project proposes a **carbon-aware, physics-guided offline reinforcement learning framework** that learns safe and deployable cooling control policies while explicitly minimizing **carbon emissions**, not just energy usage.

---

## Key Contributions
- **Carbon-aware reward formulation** that incorporates time-varying grid carbon intensity
- **Offline-only reinforcement learning** (no simulator or live system interaction)
- **Physics-guided regularization** to enforce smooth and safe control behavior
- Modular, reproducible **research codebase**
- Applicable to data centers, HVAC systems, and smart building control

---

## Motivation
- Cooling systems account for a significant fraction of data center electricity usage
- Real-world cooling systems are **safety-critical**, making online RL impractical
- Grid electricity carbon intensity fluctuates due to renewable and fossil fuel mix
- Carbon-aware control enables **emission reduction without additional hardware**

This project demonstrates how **Offline RL + sustainability-aware objectives** can enable responsible and deployable AI for real-world infrastructure.

---

## Offline Reinforcement Learning Setup

### State Space
Each state includes:
- Cold aisle temperature
- Hot aisle temperature
- Server load
- Cooling system state (fan speed / setpoints)
- Ambient conditions
- **Grid carbon intensity (kg CO₂ / kWh)**

### Action Space
- Continuous cooling control actions  
  (e.g., fan speed or temperature setpoints)

### Reward Function
The learning objective balances efficiency, emissions, and safety:

\[
R = -E
    - \lambda_1 (CI \times E)
    - \lambda_2 \text{OverheatPenalty}
    - \lambda_3 \text{InstabilityPenalty}
\]

Where:
- **E** = cooling energy consumption  
- **CI** = grid carbon intensity  
- OverheatPenalty discourages thermal violations  
- InstabilityPenalty encourages smooth control actions  

---

## Algorithms
The project focuses on **state-of-the-art offline RL methods**:
- **Implicit Q-Learning (IQL)**
- **Conservative Q-Learning (CQL)**

Both algorithms operate strictly on **fixed historical datasets** and are suitable for safety-critical control problems.

---

## Project Structure
```

carbon-aware-offline-rl-cooling/
├── configs/          # YAML-based experiment configs
├── data/             # Raw and processed offline datasets
├── envs/             # Evaluation-only environment abstractions
├── offline_rl/       # IQL and CQL implementations
├── models/           # Actor, critic, encoders, physics regularization
├── training/         # Training and evaluation loops
├── evaluation/       # Metrics, baselines, carbon analysis
├── experiments/      # Experiment definitions
├── notebooks/        # Analysis and visualization
├── scripts/          # CLI entry points
└── docs/             # Methodology and GSoC proposal

````

---

## How to Run (after implementation)

### Training
```bash
python scripts/train.py --config experiments/exp_carbon_aware.yaml
````

### Evaluation

```bash
python scripts/evaluate.py --config experiments/exp_carbon_aware.yaml
```

---

## Research Context

This project is inspired by recent advances in **offline reinforcement learning for data center cooling**, including physics-informed and safety-aware approaches validated in real-world deployments. Unlike prior work, this repository focuses on **carbon-aware optimization**, explicitly accounting for the environmental impact of electricity consumption.

---

## Intended Use

* Research project
* Sustainable AI / Green AI experimentation
* Offline RL benchmarking beyond toy environments
* Smart buildings and HVAC optimization research

---

## Disclaimer

This project is **research-oriented** and does not directly control real-world infrastructure. Any deployment in production environments requires extensive validation and safety certification.

```

---
