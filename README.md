# AI-Driven Fraud Detection & Auditable Rule Synthesis in Transit Telemetry

Master's Thesis in Computer Science and Engineering @ Politecnico di Milano

**Title:** An Explainable Sequence Learning Approach for Transit Fare Fraud Detection

**Author:** Christian Lisi  

📄 **[Read the Full Thesis (PDF)](./Master_Thesis_Christian_Lisi.pdf)**  


## Executive Summary

Modern automated fraud and anomaly detection systems frequently suffer from two major operational bottlenecks: the scarcity of labeled ground-truth data in high-volume industrial streams, and the "black-box" opacity of deep neural networks that prevents regulatory compliance and human auditing.

Developed in an industrial partnership using an authentic dataset of **9.6M+ commuter telemetry records** across the Lombardy regional railway network, this thesis introduces an end-to-end, self-supervised, and explainable deep learning architecture for transit violation and fraud discovery.

### Core Contributions & Architecture

1. **Large-Scale Behavioral Telemetry Modeling:**  
   Processed and structured over **9.6 million passenger events**, enriching raw spatial-temporal logs with external transit APIs to capture realistic commuter trajectories and behavioral baselines.
2. **Self-Supervised Sequence Representation:**  
   Architected a Bidirectional LSTM (**Bi-LSTM**) backbone trained via a masked sequence modeling objective to learn normal commuter flow dynamics directly from unlabeled data, eliminating dependence on costly manual annotations.
3. **Imbalanced Multi-Task Fine-Tuning:**  
   Fine-tuned multi-task classification heads to identify rare transit violations under severe class skew, achieving **85% macro precision** and a **Matthews Correlation Coefficient (MCC) of 0.81**, significantly outperforming static tree-based baselines.
4. **Auditable Explainable AI (XAI) & LLM Rulebook Synthesis:**  
   Engineered a post-hoc interpretability pipeline combining **SHAP** attributions with white-box **CART surrogate decision trees** (achieving **95% average behavioral fidelity** to the deep model). Integrated a Large Language Model (**LLM**) to automatically translate extracted mathematical decision rules into plain-language security rulebooks for compliance verification and operational incident triage.

## Key Results

| Metric / Capability | Outcome |
| :--- | :--- |
| **Dataset Scale** | 9.6M+ real-world industrial telemetry events |
| **Classification Precision** | **85% macro precision** under extreme class imbalance |
| **Overall Correlation** | **0.81 MCC** across multi-class violation categories |
| **Surrogate Fidelity** | **95%** average behavioral alignment via CART distillation |
| **Operational Output** | Automated natural-language security rulebooks |


## Technology Stack

* **Deep Learning & Modeling:** Python, PyTorch, Self-Supervised Learning, Fine-tuning, Bi-LSTM, MLP, Scikit-Learn
* **Explainable AI (XAI):** SHAP, CART Surrogate Decision Trees
* **LLM & Rule Synthesis:** Google GenAI SDK, Automated Prompt Engineering
* **Data Engineering:** PyArrow, Apache Parquet, Pandas, NumPy
