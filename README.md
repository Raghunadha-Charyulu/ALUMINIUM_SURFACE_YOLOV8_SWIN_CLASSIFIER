# 🛠️ YOLOv8 + Swin Transformer for Surface Defect Detection & Classification

This project implements a hybrid deep learning pipeline for **automated detection** and **classification** of aluminum surface defects using **YOLOv8** and **Swin Transformer**. It supports end-to-end functionality including training, detection, classification, Grad-CAM visualization, and performance evaluation.

---

## 📌 Table of Contents
- [Overview](#overview)
- [Architecture](#architecture)
- [Installation](#installation)
- [Dataset](#dataset)
- [Usage](#usage)
- [Model Training](#model-training)
- [Prediction & Visualization](#prediction--visualization)
- [Evaluation](#evaluation)
- [Technologies Used](#technologies-used)
- [Results](#results)

---

## 🧠 Overview

- **YOLOv8** is used to **detect defects** (cracks, dents, discoloration, etc.) in aluminum surface images.
- **Swin Transformer** classifies the detected regions into **4 categories**: `crack`, `dent`, `discoloration`, and `others`.
- **Grad-CAM** highlights the region influencing the classifier's decision.
- Performance is assessed using **confusion matrix** and **classification report**.

---

## 📊 Architecture

```plaintext
           ┌────────────┐
           │ Input Image│
           └─────┬──────┘
                 ↓
        ┌──────────────┐
        │  YOLOv8 Model│  ← Detect surface defect(s)
        └─────┬────────┘
              ↓
      ┌─────────────────┐
      │ Cropped Defect  │
      │ Region (ROI)    │
      └─────┬───────────┘
            ↓
   ┌──────────────────────┐
   │ Swin Transformer     │  ← Classify defect type
   └────────┬─────────────┘
            ↓
     ┌────────────┐
     │ Grad-CAM   │  ← Visual explanation
     └────┬───────┘
          ↓
  ┌────────────────────┐
  │ Final Output: Class│
  │ + Heatmap Overlay  │
  └────────────────────┘

# Clone the repository
git clone https://github.com/yourusername/yolov8-swin-defect-classifier.git
cd yolov8-swin-defect-classifier

# Install dependencies (Colab/Local)
pip install ultralytics torch torchvision matplotlib

## 🧰 Technologies Used

This project combines the power of cutting-edge deep learning models for real-time defect detection and classification. The following tools and frameworks were used:

- **YOLOv8 (Ultralytics)** – For fast and accurate detection of defects using object detection architecture.
- **Swin Transformer (Vision Transformer)** – For classifying detected defect regions into types such as crack, dent, discoloration, and others.
- **PyTorch** – Backbone framework for building and training the Swin Transformer model.
- **Torchvision** – For loading pre-trained vision models and applying image transformations.
- **Matplotlib** – For visualizing the Grad-CAM outputs and result overlays.
- **Grad-CAM** – For generating heatmaps to visualize the influential areas during classification.
- **Scikit-learn** – For calculating performance metrics like confusion matrix and classification report.
- **Google Colab** – Used as the development and training environment with GPU acceleration.

## 📈 Results

The model was trained and evaluated on an aluminum surface defect dataset. Here are the performance metrics achieved by the **Swin Transformer classifier** on a test subset:

| Defect Type   | Precision | Recall | F1-Score |
|---------------|-----------|--------|----------|
| Crack         | 0.91      | 0.88   | 0.89     |
| Dent          | 0.85      | 0.90   | 0.87     |
| Discoloration | 0.88      | 0.85   | 0.86     |
| Others        | 0.83      | 0.82   | 0.82     |

> 🔍 These metrics reflect model performance on 1000 test samples. Actual results may vary based on dataset quality, image resolution, and further fine-tuning.

The results demonstrate the pipeline’s robustness in not only detecting defects accurately with YOLOv8 but also classifying them effectively using Swin Transformer with interpretable Grad-CAM visualizations.



