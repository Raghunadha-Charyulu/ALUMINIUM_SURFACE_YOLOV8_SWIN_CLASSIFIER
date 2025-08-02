# 🛠️ Aluminum Surface Defect Detection & Classification (YOLOv8 + Swin Transformer)

A hybrid deep learning pipeline for automated **detection** and **classification** of aluminum surface defects using **YOLOv8** and **Swin Transformer**, with support for **Grad-CAM visualization** and evaluation metrics. This system enables accurate detection of defects like cracks, dents, discoloration, and more—designed for real-time industrial applications.

---

## 📑 Table of Contents

- [📌 Overview](#-overview)
- [🧠 Architecture](#-architecture)
- [🧰 Technologies & Dataset](#-technologies--dataset)
- [📥 Repository Cloning & Setup](#-repository-cloning--setup)
- [📊 Results](#-results)
- [📜 License](#-license)

---

## 📌 Overview

The presence of surface defects in aluminum components affects the structural integrity and usability in industries such as aerospace, automotive, and construction. Manual inspection is slow and error-prone. This project automates the detection and classification process using a two-stage deep learning approach:

- **YOLOv8** for localized detection using oriented bounding boxes.
- **Swin Transformer** for classifying the defect type.
- **Grad-CAM** to visualize important features driving the prediction.
- **Evaluation metrics** to validate model performance.

---

## 🧠 Architecture

The following represents the high-level pipeline of the system:

+----------------+ +-------------------+ +------------------------+
| Input Image | --> | YOLOv8 Detection | --> | Cropped Defect Regions |
+----------------+ +-------------------+ +------------------------+
|
v
+-----------------------------+
| Swin Transformer Classifier |
+-----------------------------+
| |
v v
+------------------------+ +----------------------+
| Defect Type Output | | Grad-CAM Visualization|
+------------------------+ +----------------------+

### 🔍 Description

- **Input Image**: Raw aluminum surface image from dataset.
- **YOLOv8 Detection**: Detects and localizes defect regions using oriented bounding boxes.
- **Cropped Regions**: The defect-specific regions are cropped for classification.
- **Swin Transformer**: Classifies each region into categories like crack, dent, discoloration, or others.
- **Grad-CAM**: Generates visual explanations for model predictions.
