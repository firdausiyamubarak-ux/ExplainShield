# ExplainShield
# 🛡️ ExplainShield — Explainable AI Malware Detector

> Detects malware with 99.4% ROC-AUC and explains every prediction using SHAP values mapped to MITRE ATT&CK tactics.

## Overview

ExplainShield is an explainable machine learning system for malware detection trained on the EMBER 2018 dataset — 1 million real-world PE file samples. Unlike black-box detectors, ExplainShield tells you **why** a file is malicious by mapping its most influential features to real-world attack techniques from the MITRE ATT&CK framework.

## Results

| Metric | Score |
|--------|-------|
| ROC-AUC | **0.9942** |
| Precision (Malware) | 0.97 |
| Recall (Malware) | 0.97 |
| F1-Score | 0.97 |
| Training Samples | 150,000 |
| Features | 2,381 |

## How It Works

1. **Feature Extraction** — 2,381 static features extracted from PE files (headers, imports, sections, strings)
2. **LightGBM Classification** — gradient boosting model trained on EMBER 2018
3. **SHAP Explainability** — per-prediction feature importance scores
4. **MITRE ATT&CK Mapping** — top features mapped to real attack techniques (T1497, T1105, T1083, T1059)

## MITRE ATT&CK Techniques Detected

| ATT&CK ID | Tactic |
|-----------|--------|
| T1497 | Virtualization/Sandbox Evasion |
| T1105 | Ingress Tool Transfer |
| T1083 | File and Directory Discovery |
| T1059 | Command & Scripting Interpreter |
| T1027 | Obfuscated Files or Information |

## Tech Stack

- **Model:** LightGBM
- **Explainability:** SHAP (TreeExplainer)
- **Dataset:** EMBER 2018 (1M PE files)
- **Threat Intel:** MITRE ATT&CK Framework
- **Interface:** Gradio
- **Environment:** Kaggle (GPU T4 x2)

## Live Demo

🔗 [Try it on HuggingFace Spaces](#) *(link coming soon)*

## Dataset

[EMBER 2018 — dhoogla/ember-2018-v2-features](https://www.kaggle.com/datasets/dhoogla/ember-2018-v2-features)

## Kaggle Notebook

🔗 [View on Kaggle](https://kaggle.com/firdausiyamubarak/explainshield-v1)

## Author

**Firdausiya Mubarak** — AI × Cybersecurity  
Building at the intersection of explainable AI and threat intelligence.
