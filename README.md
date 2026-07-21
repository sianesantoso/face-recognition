<div align="center">

# 🔍 Face Recognition using Transfer Learning & Incremental Learning

### Deep Face Recognition with **Inception ResNet V1**, **Transfer Learning**, and **Incremental Learning**

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-Deep_Learning-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![FaceNet](https://img.shields.io/badge/FaceNet-Inception_ResNet_V1-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-Research-green?style=for-the-badge)

</div>

---

## 📖 Overview

This project implements a **face recognition system** using **Inception ResNet V1** pretrained on **VGGFace2**. Instead of training a face recognition model from scratch, the network extracts **512-dimensional face embeddings**, and identities are recognized by measuring the similarity between embeddings using **Cosine Similarity**.

The project evaluates three learning strategies to improve recognition performance under challenging real-world conditions such as:

- 💡 Illumination variation
- 😊 Facial expression changes
- 🧔 Beard and hairstyle changes
- 📷 Blur
- 🔄 Pose variation
- 🌑 Low-quality images

---

# 🚀 Features

- 🧠 Face Recognition using Deep Learning
- 📌 Inception ResNet V1 pretrained on VGGFace2
- 🔄 Transfer Learning
- ➕ Incremental Learning
- 📐 Face Embedding Extraction
- 📊 Cosine Similarity Matching
- 🖼️ Data Augmentation
- 📈 Performance Comparison

---

# 🗂 Dataset

This project uses **NIST Special Database 32 (SD32)**.

The dataset consists of mugshot face images captured under different acquisition conditions, making it suitable for evaluating face recognition robustness.

> **Note**
>
> Due to the dataset license, the original images are **not included** in this repository.

Dataset documentation is available inside the **docs/** folder.

---

# 🔄 Data Augmentation

To improve model robustness, several augmentation techniques were applied during training:

- 🔁 Rotation
- ↔️ Horizontal Flip
- ☀️ Brightness Adjustment

These augmentations help the model generalize better to pose and lighting variations.

---

# 🏗 Model Architecture

## Feature Extractor

- **Inception ResNet V1**
- **Pretrained on VGGFace2**

## Recognition Pipeline

```
Input Image
      │
      ▼
Face Preprocessing
      │
      ▼
Data Augmentation (Training Only)
      │
      ▼
Inception ResNet V1
      │
      ▼
Face Embedding
      │
      ▼
Cosine Similarity
      │
      ▼
Identity Prediction
```

---

# 🧪 Experimental Methods

Three different approaches were evaluated:

| Method | Description |
|---------|-------------|
| Transfer Learning (No Augmentation) | Fine-tuning without image augmentation |
| Transfer Learning (Augmentation) | Fine-tuning with augmented training images |
| Incremental Learning | Expanding the embedding database using augmented embeddings without retraining the entire model |

---

# 📊 Experimental Results

| Method | Validation Accuracy |
|---------|--------------------:|
| Transfer Learning (No Augmentation) | **87.98%** |
| Transfer Learning (Augmentation) | **89.44%** |
| ⭐ Incremental Learning | **90.03%** |

### 📈 Performance Comparison

```
Transfer Learning (No Aug.)   ████████████████████████ 87.98%

Transfer Learning (+Aug.)     █████████████████████████ 89.44%

Incremental Learning          ██████████████████████████ 90.03%
```

Incremental Learning achieved the highest validation accuracy by enriching the embedding database with additional augmented samples while avoiding complete model retraining.

---

# 🔍 Error Analysis

## Transfer Learning

The model incorrectly classified **35 validation images**.

Major causes:

- 🌑 Low illumination
- 🌫 Motion blur
- 🔄 Different face poses
- 🧔 Beard and mustache changes
- 💇 Hairstyle changes
- 😊 Facial expression changes
- 👴 Limited age variation
- 😕 Missing frontal face images

---

## Incremental Learning

After incorporating augmented embeddings, the number of incorrect predictions decreased to **33 images**.

Remaining challenges include:

- Missing frontal face images
- Long-distance face capture
- Poor illumination
- Blur
- Facial appearance changes
- Different facial expressions
- Limited temporal variation

---

# 📁 Project Structure

```
scripts/
│
├── transfer_learning_no_augmentation.py
├── transfer_learning_with_augmentation.py
├── incremental_learning.py
├── predict.py
├── convert_ppm_to_jpeg.py
└── utils.py

docs/
│
└── Dataset Documentation

requirements.txt
README.md
```

---

# ⚙️ Installation

Clone this repository

```bash
git clone https://github.com/yourusername/face-recognition-transfer-learning.git
```

Move into the project directory

```bash
cd face-recognition-transfer-learning
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Requirements

- Python 3.10+
- PyTorch
- torchvision
- facenet-pytorch
- OpenCV
- Pillow
- NumPy
- scikit-learn
- matplotlib

---

# 🎯 Key Findings

✅ Data augmentation improved the recognition accuracy compared to standard transfer learning.

✅ Incremental Learning achieved the best performance without requiring complete retraining.

✅ Cosine Similarity proved effective for matching high-dimensional face embeddings extracted from Inception ResNet V1.

---

# 🔮 Future Work

- ArcFace
- AdaFace
- Face Alignment
- Automatic Similarity Threshold Optimization
- Larger Face Datasets
- More Diverse Age Variations
- Cross-Dataset Evaluation

---

# 📜 License

This repository is intended for **educational and research purposes**.

The NIST SD32 dataset is **not redistributed** due to licensing restrictions.

---

<div align="center">

### ⭐ If you found this project useful, consider giving it a star!

</div>
