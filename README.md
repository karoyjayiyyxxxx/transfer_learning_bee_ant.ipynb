# 🐜 Ants vs Bees Classifier: Transfer Learning with PyTorch

![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

## 📖 Project Overview (專案簡介)
This project demonstrates the power of **Transfer Learning** to classify images of ants and bees with high accuracy, using a very small dataset.

By fine-tuning a pre-trained **ResNet18** model (originally trained on ImageNet), we achieved **~93% accuracy** with only ~120 training images per class. This approach significantly reduces training time and data requirements compared to training a model from scratch.

## 🚀 Key Features
* **Transfer Learning:** Fine-tuning a pre-trained ResNet18 model.
* **Data Augmentation:** Using `torchvision.transforms` for resizing, flipping, and normalization.
* **Visualization:** Includes scripts to visualize prediction results.
* **GPU Accelerated:** Optimized for Google Colab (T4 GPU).

## 📂 Dataset
The dataset used is the **Hymenoptera Data** provided by the PyTorch official tutorial.
* **Classes:** Ants 🐜, Bees 🐝
* **Training set:** ~120 images per class
* **Validation set:** ~70 images per class
* **Source:** [Download Link](https://download.pytorch.org/tutorial/hymenoptera_data.zip)

## 🧠 Model Architecture
* **Base Model:** ResNet18 (Pre-trained).
* **Modification:** The final Fully Connected (FC) layer was replaced to output 2 classes.
* **Training Strategy:** * Feature Extraction layers were frozen (`requires_grad=False`).
    * Only the final FC layer was updated during training.

## 📊 Results
* **Best Validation Accuracy:** **93.46%** (Achieved at Epoch 3).
* **Observations:** The model converges very quickly. Overfitting may occur if trained for too many epochs without a scheduler on such a small dataset.

## 🛠️ How to Run
### Option 1: Google Colab (Recommended)
You can directly open and run the notebook in Google Colab:

