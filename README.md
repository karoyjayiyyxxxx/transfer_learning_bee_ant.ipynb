# transfer_learning_bee_ant.ipynb

# 🐜 Ants vs Bees Classifier: Transfer Learning with PyTorch

![PyTorch](https://img.shields.io/badge/PyTorch-%23EE4C2C.svg?style=for-the-badge&logo=PyTorch&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Colab](https://img.shields.io/badge/Colab-F9AB00?style=for-the-badge&logo=googlecolab&logoColor=white)

## 📖 Project Overview
This project demonstrates the power of **Transfer Learning** (a technique often used in Few-Shot Learning scenarios) to classify images of ants and bees with high accuracy, using a very small dataset.

By utilizing a pre-trained **ResNet18** model, we achieved **~93% accuracy** with only ~120 training images per class, significantly reducing training time and data requirements compared to training from scratch.

## 🚀 Key Features
* **Transfer Learning:** Fine-tuning a pre-trained ResNet18 model (trained on ImageNet).
* **Data Augmentation:** Using `torchvision.transforms` for resizing, flipping, and normalization to improve generalization.
* **Visualization:** Scripts to visualize prediction results directly in the notebook.
* **Environment:** Optimized for Google Colab (GPU support).

## 📂 Dataset
The dataset used is the **Hymenoptera Data** provided by the official PyTorch tutorial.
* **Classes:** Ants 🐜, Bees 🐝
* **Training set:** ~120 images per class
* **Validation set:** ~70 images per class
* **Source:** [Download Link](https://download.pytorch.org/tutorial/hymenoptera_data.zip)

## 🧠 Model Architecture
* **Base Model:** ResNet18 (Pre-trained on ImageNet).
* **Modification:** The final Fully Connected (FC) layer was replaced to output 2 classes (Ants/Bees).
* **Training Strategy:** * Feature Extraction layers were frozen (`requires_grad=False`).
    * Only the final FC layer was trained using the new dataset.

## 📊 Results
* **Best Validation Accuracy:** **93.46%** (Achieved at Epoch 3).
* **Observations:** The model learns very quickly. Overfitting may occur if trained for too many epochs without a learning rate scheduler, as observed in later epochs.
