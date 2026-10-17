# Detection of Alzheimer’s and Parkinson’s Disease from MRI Images Using Deep Learning

A thesis project exploring transfer learning for three-class MRI image classification: **Alzheimer’s disease**, **Parkinson’s disease**, and **normal controls**. The project compares several convolutional neural network (CNN) architectures and uses LIME to help interpret individual model predictions.

> **Research prototype only:** This project is for academic and experimental purposes. It is not a clinically validated diagnostic system and must not be used to diagnose, treat, or make medical decisions about any person.

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Models Evaluated](#models-evaluated)
- [Methodology](#methodology)
- [Evaluation](#evaluation)
- [Explainability with LIME](#explainability-with-lime)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Results and Reproducibility](#results-and-reproducibility)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [Acknowledgements](#acknowledgements)

## Overview

The project investigates whether transfer-learning-based CNNs can distinguish MRI images belonging to three categories:

1. Alzheimer’s disease (AD)
2. Parkinson’s disease (PD)
3. Normal controls

The repository contains Jupyter notebooks for model experiments, evaluation outputs, confusion matrices, training curves, prediction arrays, and LIME visualizations. Both augmented and non-augmented experiment folders are included.

## Objectives

- Build and evaluate deep-learning models for three-class MRI image classification.
- Compare transfer-learning architectures under the project’s experimental setup.
- Explore data augmentation as an approach to address class imbalance.
- Evaluate model performance using multiple classification metrics.
- Visualize model behavior with LIME-based explanations.

## Models Evaluated

The notebooks cover the following CNN architectures:

- **InceptionV3**
- **ResNet50**
- **VGG19**
- **MobileNetV2**
- **Xception**

The experiments use transfer learning with pretrained ImageNet weights, followed by training/fine-tuning for the MRI classification task.

## Methodology

### 1. Data preparation

The project uses MRI images organized into three classes: Alzheimer’s disease, Parkinson’s disease, and normal controls. The notebooks include image preparation and experiments with augmented data.

### 2. Data augmentation

Augmented experiments apply image transformations such as rotation, flipping, and scaling to help address class imbalance and improve training robustness. The exact preprocessing and training settings may differ between notebooks, so consult the relevant notebook when reproducing a particular experiment.

### 3. Model training

Each architecture is trained and evaluated in its corresponding Jupyter notebook. The repository contains separate experiment artifacts for augmented and non-augmented models.

### 4. Evaluation

The project records a range of metrics and visualizations, including:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrices
- Training/validation accuracy and loss curves
- Additional metrics recorded by the notebooks, including Hamming loss, Cohen’s kappa, Matthews correlation coefficient (MCC), and Jaccard score where implemented

## Explainability with LIME

The `LIME/` directory contains visual explanation images for examples from the Alzheimer’s disease, Parkinson’s disease, and control categories. LIME (Local Interpretable Model-agnostic Explanations) can highlight image regions that influenced a particular prediction. These visualizations are exploratory explanations, not proof that a model has learned medically valid features.

## Repository Structure

The repository includes the following main components:

```text
.
├── Augmented Model Files/
│   ├── AugInceptionV3/
│   ├── AugMobileNetV2/
│   ├── AugResNet50/
│   ├── AugVGG19/
│   └── AugXception/
├── Model Files/
│   ├── InceptionV3/
│   ├── MobileNetV2/
│   ├── ResNet50/
│   ├── VGG19/
│   └── Xception/
├── LIME/
│   ├── AD*.png
│   ├── PD*.png
│   └── CON*.png
└── README.md
```

Each model directory may contain a Jupyter notebook, recorded metrics, prediction arrays, confusion matrices, and training/validation plots. Exact contents vary by experiment.

## Getting Started

### Requirements

The experiments are implemented in Python notebooks and use common deep-learning and data-science libraries, including:

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Matplotlib
- scikit-learn
- OpenCV
- Jupyter Notebook
- LIME (for explainability experiments)

The exact package versions are not specified in a single dependency lockfile in this repository. For reproducibility, use an isolated Python environment and install compatible versions for the notebook code.

### Run the experiments

1. Clone or download this repository.
2. Install Python and Jupyter Notebook, along with the libraries required by the notebook you want to run.
3. Open the relevant `.ipynb` file under `Model Files/` or `Augmented Model Files/`.
4. Update any dataset or file paths to match your local setup.
5. Run the notebook cells in order.
6. Review the generated metrics, confusion matrices, training curves, and prediction outputs.

**Dataset note:** Check the repository contents and notebook paths for the MRI dataset. If the dataset is not included, obtain it from the original authorized source and update the notebook paths. Ensure you have permission to use and redistribute any dataset.

## Results and Reproducibility

The repository contains per-model evaluation artifacts, including metric records and confusion matrices. Results can vary between the augmented and non-augmented experiments and depending on preprocessing, data splits, and training settings.

For this reason, this README does not claim a single best accuracy figure. Refer to the relevant notebook and its saved evaluation outputs for the specific experiment you wish to report. When citing a metric, state the model variant, whether augmentation was used, and the evaluation split.

## Limitations

- The repository represents an academic research prototype, not a clinically validated tool.
- Model performance depends on dataset quality, class balance, preprocessing, and evaluation design.
- Results from one dataset may not generalize to other scanners, hospitals, populations, or acquisition protocols.
- LIME visualizations are interpretability aids and should not be treated as clinical evidence.
- A reported classification result does not establish that the model is safe or suitable for real-world diagnosis.

## Future Work

Potential extensions include:

- Testing on larger, more diverse, independently sourced datasets.
- Using patient-level separation and external validation where metadata permits.
- Improving experiment tracking and documenting package versions, random seeds, preprocessing, and data splits.
- Comparing models with consistent evaluation protocols and reporting per-class metrics.
- Developing a reproducible inference interface only after appropriate validation and safeguards.

## Acknowledgements

The original project README acknowledges **Mahruba Sharmin Chowdhury** for supervision and **Abdullah Al Noman** for guidance during the project.

---

**Disclaimer:** This repository is intended for education and research. It is not a substitute for professional medical advice, diagnosis, or treatment.
