# A Distilled, Quantization-Aware TinyML Framework for Ultra-Low-Power Threat Detection in IoMT Edge Sensors

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-EE4C2C.svg)](https://pytorch.org/)

> **Official code repository for the manuscript:** *"A Distilled, Quantization-Aware TinyML Framework for Ultra-Low-Power Threat Detection in IoMT Edge Sensors."* 

## 📌 Overview
The rapid expansion of the Internet of Medical Things (IoMT) has exposed life-critical healthcare networks to severe edge-level vulnerabilities, including biometric spoofing and MQTT telemetry injection. This repository provides the complete PyTorch implementation of a **Knowledge-Distilled, Quantization-Aware TinyML framework** designed to intercept these attacks directly on resource-constrained microcontrollers (MCUs) at the extreme edge.

By transferring spatial-temporal intelligence from a heavy Temporal Graph Convolutional Network (Teacher) to a highly constrained 1D-Depthwise Convolutional GRU (Student), this framework achieves a **78.69× structural compression factor**.

### 🚀 Key Performance Metrics
| Metric | Teacher (TGCN FP32) | Student (TinyML INT8) |
| :--- | :--- | :--- |
| **Parameters** | 607,938 | 7,726 |
| **Memory Footprint** | ~2.4 MB | **34.37 KB** |
| **Detection Accuracy** | > 98% | **93.49%** |
| **Inference Latency** | N/A (Cloud) | **~5 ms / sequence** |

## 📂 Repository Structure
- `/analysis`: Data exploration scripts and results, including the feature interdependency (correlation) matrix and Explainable AI (XAI) permutation importance outputs.
- `/checkpoints`: Pre-trained PyTorch model weights, including the Teacher Oracle (TGCN FP32), distilled Student (FP32), and final extreme-edge Student (INT8).
- `/figures`: High-resolution visual artifacts generated during execution (e.g., Pareto Frontier, KD loss convergence, ROC/PR curves, and the Confusion Matrix).
- `/logs`: Training history records, loss convergence metrics, and hardware profiling logs detailing the 5 ms execution latency.
- `/tables`: Raw CSV outputs containing classification reports, precision/recall summaries, and exact physical hardware footprint measurements.
- `pipeline.ipynb`: The complete, end-to-end Jupyter notebook covering the entire methodology (Data Engineering -> Knowledge Distillation -> Quantization-Aware Training -> INT8 Static Export).
- 
## ⚙️ Installation & Requirements
Clone the repository and install the required dependencies:

```bash
git clone https://github.com/mahiealam/TinyML-QAT-IoMT-Security.git
cd TinyML-QAT-IoMT-Security
pip install -r requirements.txt
