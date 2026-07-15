# GridSentinel-AI: Agentic Defense for Distribution Networks ⚡

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**GridSentinel-AI** is a stateful, multi-agent framework designed to detect, localize, and mitigate cyber-physical threats in smart grid distribution networks. Built using LangGraph, PyTorch, and Llama 3 (via Ollama), this platform closes the gap between raw anomaly detection and physically verified grid stabilization.

## 📖 Overview

Distribution networks are increasingly vulnerable to sophisticated attacks, including:
* **False Data Injection (FDI)** (e.g., Price/Market Manipulation)
* **Proportional Power Theft** (e.g., Smart Meter Hacks)
* **Load-Altering Attacks** (e.g., Inverter Blinding)
* **Synchronization Lag** (e.g., Time Spoofing)

Existing solutions operate as single-shot classifiers that raise alerts but do not formulate safe responses. GridSentinel-AI utilizes a **4-Node Cyber-Physical Architecture** to autonomously diagnose attacks and verify mitigation commands using a deterministic Digital Twin.

## 🏗️ Architecture

1.  **Physics Detection Node (PyTorch):** An autoencoder that acts as a "numeric-veto" guardrail, calculating Spatio-Temporal Mean Squared Error (MSE) to flag deviations from baseline operations.
2.  **Forensics Agent (Llama 3):** Analyzes the mathematical deviation fingerprint to diagnose the specific attack vector and pinpoint the compromised asset.
3.  **Defense Agent (Llama 3):** Proposes a network defense protocol (e.g., `DIGITAL_TWIN_OVERRIDE` or `ASSET_ISOLATION`).
4.  **Verification Node:** Simulates the AI's proposed defense on the physical tensor, recalculating the grid's MSE to ensure stabilization before deployment.

## 🚀 Quick Start

### Prerequisites
* Python 3.10+
* [Ollama](https://ollama.com/) installed locally with `llama3` pulled (`ollama run llama3`)

### Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/YOUR-USERNAME/GridSentinel-AI.git](https://github.com/YOUR-USERNAME/GridSentinel-AI.git)
   cd GridSentinel-AI