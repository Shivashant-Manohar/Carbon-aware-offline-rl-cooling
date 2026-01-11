# Carbon-Aware Offline Reinforcement Learning for Data Center Cooling

## Overview
Data center cooling systems account for 30–40% of total data center energy consumption.  
Most existing control strategies optimize only for energy efficiency and rely on online interaction or high-fidelity simulators, which are unsafe or impractical in real-world deployments.

This project proposes a **carbon-aware, physics-guided offline reinforcement learning framework** that learns safe cooling control policies **solely from historical data**.  
The system explicitly accounts for **time-varying electricity carbon intensity**, enabling emission-aware cooling decisions without compromising thermal safety.

This repository is designed as a **research codebase**:
- Fully offline (no environment interaction during training)
- Safety-aware (thermal constraint penalties)
- Carbon-aware (grid CO₂ intensity integrated into reward)
- Physics-guided (lightweight domain regularization)
- Modular and reproducible

---

## Key Contributions
- Carbon-aware reward shaping for offline RL
- Safe cooling optimization using historical HVAC data only
- Physics-inspired regularization for stable control
- Reproducible research pipeline suitable for real-world deployment

---

## Project Structure
