# Cyber-security-lab-1

# Evaluating Privacy Vulnerabilities in Federated Learning via Gradient Inversion Attacks

This repository contains the source code and reproducibility framework for the Cybersecurity Labs I project at Eötvös Loránd University (ELTE). 

The project demonstrates that sharing gradients in Federated Learning (FL) is mathematically equivalent to sharing raw training data. It implements a state-of-the-art Gradient Inversion Attack (Deep Leakage from Gradients) optimized with Cosine Similarity and Total Variation (TV) regularization to reconstruct private client data with high visual fidelity.

## Features & Implemented Attacks
* **Baseline Gradient Inversion:** Reconstructs CIFAR-10 images from intercepted gradients using the L-BFGS optimizer.
* **Analytical Label Leakage:** Deterministically extracts private classification labels instantly by exploiting cross-entropy bias gradients.
* **Comparative Analysis (Batch Size):** Simulates attack degradation when clients utilize larger batch sizes (e.g., Batch Size = 4) to obfuscate their gradient footprint.
* **Differential Privacy (DP) Defense:** Simulates a defense-in-depth approach by applying calibrated Gaussian noise to true gradients to measure the exact threshold of attack failure.
* **RDLV Evaluation:** Includes a custom Relative Data Leakage Value (RDLV) metric, scaling MSE against ground-truth variance to calculate privacy loss as a percentage alongside standard PSNR metrics.

## Dependencies
To reproduce the experiments in this repository, you need a Python environment with GPU support (CUDA recommended) and the following libraries:
* `torch`
* `torchvision`
* `matplotlib`
* `numpy`

## Reproducibility and Execution
The entire experimental framework is contained within the `csl1.ipynb` Jupyter Notebook. To reproduce the results:
1. Clone this repository or open the notebook directly in Google Colab.
2. Run the cells sequentially from top to bottom.
3. **Note on Dataset:** The notebook automatically downloads the CIFAR-10 dataset via `torchvision`. If you encounter a 503/404 error from the official servers, uncomment the AWS mirror patch provided in the Setup cell.

## Author
* **Yehor Danilenko**
* **Supervisor:** Dr. Mohammed Alshawki
* **Course:** Cyber Security Labs I (IPM-22FKBSCLAB1) - ELTE Faculty of Informatics
* 
