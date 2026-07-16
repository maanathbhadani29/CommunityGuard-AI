# CommunityGuard-AI: Agentic Defense for Building Communities 🏙️

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**CommunityGuard-AI** is a stateful, multi-agent AI framework designed to detect, localize, and mitigate cyber-physical threats in smart building communities. Built using LangGraph, PyTorch, and Llama 3 (via Ollama), this platform provides autonomous, physically-verified security for connected energy assets at the grid edge.

## 📖 Overview

As neighborhoods transition into interconnected "building communities" and Virtual Power Plants (VPPs), the edge devices managing these buildings become vulnerable to sophisticated cyberattacks, including:
* **Price/Market Manipulation** (e.g., Corrupting automated bidding signals)
* **Smart Meter Hacks** (e.g., Stealthy load-siphoning)
* **Inverter Blinding** (e.g., Destabilizing building solar generation)
* **Time Spoofing** (e.g., Desynchronizing building energy schedules)

Because we do not simulate raw power system distribution networks, this project focuses strictly on the energy management and telemetry at the building level. CommunityGuard-AI utilizes a **4-Node Cyber-Physical Architecture** to diagnose attacks and verify mitigation commands using a deterministic CityLearn Digital Twin.

## 🏗️ Architecture

1.  **Physics Detection Node (PyTorch):** An autoencoder that monitors building telemetry, calculating Spatio-Temporal Mean Squared Error (MSE) to flag deviations from a normal building's energy baseline.
2.  **Forensics Agent (Llama 3):** Analyzes the mathematical deviation fingerprint to diagnose the specific attack vector and pinpoint the compromised building.
3.  **Defense Agent (Llama 3):** Proposes an edge-device defense protocol (e.g., `DIGITAL_TWIN_OVERRIDE` or `ASSET_ISOLATION`).
4.  **Verification Node:** Simulates the AI's proposed defense using the CityLearn environment, recalculating the community's MSE to ensure the building's energy profile is stabilized before deployment.

## 🚀 Quick Start

### Prerequisites
* Python 3.10+
* [Ollama](https://ollama.com/) installed locally with `llama3` pulled (`ollama run llama3`)
* `CityLearn==2.0.0`

### Execution
Run the Master Pipeline via Jupyter Notebook to simulate the community environment, train the anomaly detector, and execute the autonomous LangGraph agents:
```bash
jupyter notebook src/communityguard_pipeline.ipynb