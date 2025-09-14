# Mind the Gaps: AI-Driven Detection of Kubernetes Misconfigurations

This repository contains the **final project for the course "Methods For Detecting Attacks" (2025)**.  
It explores how **large language models (LLMs)** can detect misconfigurations and potential **attack surfaces** in Kubernetes manifests, going beyond traditional static scanners.

📖 **Important**: This is not a published paper but a **course final project**.  
For full details, please read the report:  
[mind_the_gaps_ai_kubernetes_misconfig_detection.pdf](mind_the_gaps_ai_kubernetes_misconfig_detection.pdf)

---

## 🚀 Overview
- **Problem**: Misconfigured Kubernetes manifests can create serious **security** and **operational** risks, and may be exploited in real-world attacks.  
- **Approach**: Fine-tune [CodeBERT](https://arxiv.org/abs/2002.08155) for **multi-label classification** of misconfigurations.  
- **Data**: Kubernetes YAML manifests annotated with errors from 3 scanners:
  - [KubeLinter](https://github.com/stackrox/kube-linter)  
  - [Terrascan](https://github.com/tenable/terrascan)  
  - [Checkov](https://www.checkov.io)  

- **Contributions**:
  - Corrected noisy labels through **manual verification guided by model predictions**  
  - Applied **transfer learning** for high accuracy with limited labeled data  
  - Demonstrated that LLMs can detect **attack-relevant misconfigurations** not flagged by static scanners  
  - ⚡ **Discovered bugs in Checkov**: our LLM identified real misconfigurations that Checkov falsely ignored, highlighting limitations in current rule-based tools  

- **Results**: Achieved **~0.99 F1 score**, with strong ranking metrics (LRAP ≈ 0.99).

---