# EN3160 – Assignment 03: Deep Learning for Image Classification

**Department of Electronic and Telecommunication Engineering**  
**University of Moratuwa**

An implementation and experimental evaluation of Convolutional Neural Networks (CNNs) and transfer learning techniques for image classification using **PyTorch**.

## Overview

This assignment explores deep learning techniques for image classification, focusing on CNN architecture design, training, evaluation, and transfer learning.

The experiments investigate the performance of classical and modern CNN architectures and compare different approaches to adapting pretrained deep learning models.

The complete implementation, training procedures, visualizations, and experimental results are available in the Jupyter notebook.

## Implemented Models and Experiments

### 1. LeNet-5 Architecture

Implementation of the classical LeNet-5 CNN architecture for image classification.

Key components:
- Convolutional layers for feature extraction
- Pooling layers for spatial downsampling
- Fully connected layers for classification
- Model training and performance evaluation

### 2. LeNet-5 vs. Modern CNN

A comparative experiment between the classical LeNet-5 architecture and a more modern CNN.

The Modern CNN incorporates:
- Multiple convolutional layers with 3×3 kernels
- Batch Normalization
- ReLU activation functions
- Max Pooling
- Dropout regularization
- Fully connected classification layers

**Experimental Results**

| Model | Training Accuracy | Test Accuracy |
|---|---:|---:|
| LeNet-5 | 99.38% | 98.46% |
| Modern CNN | 99.11% | **99.48%** |

The Modern CNN achieved higher test accuracy, demonstrating improved generalization in this experiment.

### 3. Transfer Learning with ResNet-18

Transfer learning experiments using a pretrained **ResNet-18** architecture.

Two approaches were evaluated:

**Fine-tuning**
- Updates the pretrained model's parameters during training.
- Allows the model to adapt its learned features to the target dataset.

**Feature Extraction**
- Freezes the pretrained backbone.
- Trains only the final classification layer.
- Requires significantly fewer trainable parameters.

**Experimental Results**

| Metric | Fine-tuning | Feature Extraction |
|---|---:|---:|
| Best Validation Accuracy | 94.12% | **94.77%** |
| Training Time | 29.83 s | 35.01 s |
| Trainable Parameters | 11,177,538 | 1,026 |

Feature extraction achieved slightly higher validation accuracy with substantially fewer trainable parameters in this experiment. However, the measured execution time was slightly longer.

These results are specific to the training configuration and dataset used.

## Technologies Used

- Python
- PyTorch
- Torchvision
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook / Google Colab
- CUDA (GPU acceleration, when available)

## Repository Structure

```text
EN3160_Assignment_3/
├── EN3160_Assignment_3.ipynb
└── README.md
```

## Running the Notebook

### Option 1: Google Colab

Open the notebook directly in Google Colab:

[Open in Google Colab](https://colab.research.google.com/github/AkhilaNisal/EN3160_Assignment_3/blob/main/EN3160_Assignment_3.ipynb)

Enable GPU acceleration where available:

`Runtime → Change runtime type → GPU`

Run the notebook cells sequentially.

### Option 2: Local Environment

Clone the repository:

```bash
git clone https://github.com/AkhilaNisal/EN3160_Assignment_3.git
cd EN3160_Assignment_3
```

Install the main dependencies:

```bash
pip install torch torchvision numpy matplotlib scikit-learn jupyter
```

Launch Jupyter:

```bash
jupyter notebook EN3160_Assignment_3.ipynb
```

Additional dataset downloads may be required when executing the notebook.

## Evaluation Metrics

The experiments use classification accuracy and training/validation loss to evaluate model performance.

Training curves and accuracy comparisons help identify model convergence, overfitting, and generalization behavior.

## Key Observations

- Modern CNN components such as Batch Normalization and Dropout can help improve training and generalization.
- Increasing architectural complexity does not always guarantee better performance.
- Transfer learning makes it possible to reuse features learned from large-scale datasets.
- Feature extraction can substantially reduce the number of trainable parameters compared with full fine-tuning.
- Model performance depends on dataset characteristics, architecture, optimization settings, and training configuration.

## Author

**Akhila Nisal Wedamestrige**  
Electronic and Telecommunication Engineering Undergraduate  
University of Moratuwa

GitHub: [AkhilaNisal](https://github.com/AkhilaNisal)

---

*Academic coursework – EN3160: Image Processing and Machine Vision, University of Moratuwa.*
