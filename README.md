# ExplainShield
# 🛡️ ExplainShield — Explainable AI Malware Detector

> Detects malware with 99.4% ROC-AUC and explains every prediction using SHAP values mapped to MITRE ATT&CK tactics.

## The Problem

Cyberattacks cost the global economy over $8 trillion in 2023. Traditional antivirus tools rely on known signatures — they fail against new, never-seen-before malware. Modern AI detectors improve accuracy but operate as black boxes: they flag a file as malicious but cannot explain why. Security analysts are left blind, unable to understand the threat, respond effectively, or improve defenses.

## What ExplainShield Does

ExplainShield combines high-accuracy malware detection with full transparency. It doesn't just detect — it explains. Every prediction comes with a ranked list of features that drove the decision, mapped directly to real-world attack techniques from the MITRE ATT&CK framework used by cybersecurity professionals worldwide.

This means a security analyst can see not just "this file is malware" but "this file is malware because it exhibits sandbox evasion behavior (T1497), attempts to transfer tools remotely (T1105), and probes the file system (T1083)."

## Real-World Impact

- Speeds up incident response by giving analysts actionable threat context
- Bridges the gap between AI and human decision-making in cybersecurity
- Applicable in SOC environments, threat hunting, and malware research
- Contributes to building safer digital infrastructure globally

## Why This Matters Globally

Cybersecurity is not just a technical problem — it is a human one. In developing countries, hospitals, schools, and government institutions are increasingly targeted by malware attacks with no resources to defend themselves. ExplainShield was built with this in mind: an open, explainable tool that doesn't require a PhD to understand, making AI-powered threat detection accessible to defenders everywhere.

As a student from India building tools that address global security challenges, this project reflects my belief that technology should serve people — not just those with resources, but communities worldwide that depend on secure digital infrastructure.

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

1. **Feature Extraction** — 2,381 static features from PE file headers, imports, sections, and strings
2. **LightGBM Classification** — gradient boosting model trained on EMBER 2018
3. **SHAP Explainability** — per-prediction feature importance using TreeExplainer
4. **MITRE ATT&CK Mapping** — top features mapped to real attack techniques

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

## Kaggle Notebook

🔗 [View on Kaggle](https://kaggle.com/firdausiyamubarak/explainshield-v1)

## Dataset

[EMBER 2018 — dhoogla/ember-2018-v2-features](https://www.kaggle.com/datasets/dhoogla/ember-2018-v2-features)

## Author

**Firdausiya Mubarak** — AI × Cybersecurity  
Building explainable AI systems at the intersection of machine learning and global cybersecurity.
