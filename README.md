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

| Tool/Library         | Purpose                                  |
| -------------------- | ---------------------------------------- |
| YOLOv8 (Ultralytics) | Object detection (defect bounding boxes) |
| Swin Transformer     | Image classification                     |
| PyTorch              | Model training/inference                 |
| Matplotlib           | Visualizations                           |
| Grad-CAM             | Interpretability                         |
| Scikit-learn         | Evaluation metrics                       |

| Class         | Precision | Recall | F1-score |
| ------------- | --------- | ------ | -------- |
| Crack         | 0.91      | 0.88   | 0.89     |
| Dent          | 0.85      | 0.90   | 0.87     |
| Discoloration | 0.88      | 0.85   | 0.86     |
| Others        | 0.83      | 0.82   | 0.82     |



