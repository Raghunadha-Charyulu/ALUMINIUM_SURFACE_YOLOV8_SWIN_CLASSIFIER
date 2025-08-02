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

---

## 🧰 Technologies & Dataset

### 🔧 Technologies Used

- **Python** – Core programming language
- **YOLOv8 (Ultralytics)** – For defect detection using oriented bounding boxes
- **Swin Transformer (TorchVision)** – For classifying cropped defect regions
- **Grad-CAM** – For visualizing important regions contributing to classification
- **PyTorch & TorchVision** – Deep learning model implementation and training
- **Google Colab** – Cloud-based training and experimentation environment
- **Matplotlib & PIL** – Image processing and visualization
- **Scikit-learn** – For computing evaluation metrics (Precision, Recall, F1-Score)

---

### 📁 Dataset Requirements

- **Dataset Source**: Exported from [Roboflow](https://roboflow.com/)
- **Format**: YOLOv8 Oriented Bounding Box (OBB)
- **Structure**:
  - `train/` – Training images and labels
  - `valid/` – Validation images and labels
  - `test/` – Testing images and labels
  - `data.yaml` – Contains class names and dataset paths
- **Classes**:
  - `crack`
  - `dent`
  - `discoloration`
  - `others`

---

## 📥 Repository Cloning & Setup

### 🔧 Clone the Repository

git clone https://github.com/your-username/aluminum-defect-detector.git
cd aluminum-defect-detector

## 📦 Dependencies

Make sure the following libraries are installed to run the project successfully:

### 🧪 Core Libraries

- `torch` – For model building and training
- `torchvision` – For pretrained models like Swin Transformer
- `ultralytics` – For YOLOv8 detection
- `numpy` – For numerical operations
- `matplotlib` – For visualizations
- `Pillow (PIL)` – For image loading and processing
- `scikit-learn` – For evaluation metrics (Precision, Recall, F1-Score)

### 🛠️ Installation

You can install all dependencies using:

pip install torch torchvision ultralytics matplotlib scikit-learn pillow

---

## 📊 Results

The following table summarizes the performance of the detection and classification pipeline:

| Component         | Metric     | Value  |
|------------------|------------|--------|
| YOLOv8 Detection | mAP@0.5    | 92%    |
| Swin Transformer | Accuracy   | 89%    |
|                  | F1-Score   | 88.7%  |
|                  | Precision  | 90.1%  |
|                  | Recall     | 87.2%  |

### 📌 Observations

- The **YOLOv8** model achieved high mean average precision, indicating robust defect localization performance.
- The **Swin Transformer** classifier performed well on fine-grained defect classification, especially on cropped regions.
- **Grad-CAM** visualizations confirmed that the model focuses on relevant defect features during prediction.

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

