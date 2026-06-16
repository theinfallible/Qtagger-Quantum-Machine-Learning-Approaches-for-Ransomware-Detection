# QTagger: Quantum Machine Learning Approaches for Ransomware Detection

Official codebase for the research paper: "Quantum Machine Learning Approaches for Ransomware Detection: A Comprehensive Study on RANSAP, RANSMAP, and MLRAN Datasets."

## Overview

QTagger is an empirical benchmarking framework that investigates the efficacy of Quantum Machine Learning (QML) in detecting ransomware. By utilizing hybrid quantum-classical architectures, specifically a Hybrid Quantum-Attention Network (HQAN) and a Quantum Support Vector Machine (QSVM) with domain-specific ZZ-feature mapping, this project demonstrates quantum generalization advantages in data-scarce (few-shot) security environments.

### Key Achievements

* **97.64% peak accuracy** on behavioral API logs (MLRAN) using HQAN.
* **96.01% accuracy** on storage-level logs (RANSAP SSD) using QSVM.
* **Superior generalization** (few-shot learning robustness) compared to classical Gradient Boosting baselines.

## Repository Architecture

The repository is structured into specific execution pipelines to guarantee reproducibility, as referenced in the paper's Appendix:

### 1_RANSAP_Benchmarks/
Contains the core execution loops and quantum model evaluations for the RANSAP storage dataset.
* **Notebook 1 to 5:** Covers Binary, Multi-Class, and Few-Shot evaluations for QNN and QSVM.
* **Notebook 2:** Houses the 5-fold cross-validation pipeline for SSD-backed binary classification, proving the highly stable $92.38\% \pm 0.26\%$ HQAN metric.

### 2_Classical_Baselines/
Standard ML baselines for comparison and few-shot capability testing.
* **Classical Benchmarking & Notebook 6:** Direct performance comparison using XGBoost, Random Forest, and Classical SVM.

### 3_MLRAN_HQAN_Optimization/
Targets the high-dimensional behavioral API logs.
* **Notebook 7:** Contains the execution logs achieving 97.64% accuracy, including the optimized pre-training weights and adaptive batch sizing logic for the HQAN.

### 4_RANSMAP_Scalability_and_Hardware/
Stress-tests the quantum state space against multi-class complexities and edge hardware constraints.
* **Notebooks 8 & 10:** Evaluates models strictly on Celeron vs. Core i3 hardware limits.
* **Notebooks 11 & 12:** Contains logs documenting memory limitations and fractional data evaluations when mapping 12 and 26 distinct ransomware families.

## Installation & Setup

To run the notebooks locally, we recommend setting up a virtual environment (Anaconda/Miniconda).

```bash
# Clone the repository
git clone https://github.com/YourUsername/Qtagger-Quantum-Machine-Learning-Approaches-for-Ransomware-Detection.git
cd Qtagger-Quantum-Machine-Learning-Approaches-for-Ransomware-Detection

# Create and activate a virtual environment
conda create -n qtagger_env python=3.9
conda activate qtagger_env

# Install required dependencies
pip install -r requirements.txt
# Note: GPU acceleration requires a CUDA-compatible NVIDIA GPU and the lightning.qubit plugin configured for PennyLane.
```

### Datasets
Due to storage constraints and licensing, the full RANSAP, RANSMAP, and MLRAN datasets are not hosted directly in this repository.

You can request access to the original datasets from their respective authors as cited in the paper.

Place the downloaded `.npy` or `.csv` arrays inside the `data/` directory before executing the notebooks.

### Citation
If you utilize this codebase or our HQAN methodology in your research, please cite our paper:

### Acknowledgments
Supported by the QIntern 2025 program. Special thanks to Dr. Simranjit Singh (NIT Jalandhar) and Dr. Mohit Sajwan (NSUT Delhi).
