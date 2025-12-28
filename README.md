# 🛄 Baggage X-Ray Object Detection (Dual-View)

![Project Status](https://img.shields.io/badge/Status-In%20Progress-yellow)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0.1-red)
![License](https://img.shields.io/badge/License-MIT-green)
![Dataset](https://img.shields.io/badge/Dataset-DVXray-orange)
![Fine-tuning](https://img.shields.io/badge/Fine--tuning-Yes-brightgreen)

---

## 🌟 Overview
This repository contains a **dual-view object detection model for baggage X-ray images** using a **Transformer-based architecture**, inspired by the paper:  
*“Transformer-based dual-view X-ray security inspection image analysis”* 📄

The model processes **two complementary views (OL + SD)** of baggage scans and predicts **object classes and bounding boxes**.  
Currently, the model is **being fine-tuned** on the DVXray dual-view dataset 🛠️.

---

## 🖼️ Sample Dataset Image
Here is an example of **dual-view X-ray images** (OL + SD):  

![Sample DVXray Dual-View](https://github.com/SaynaSarvar/baggage-X-ray-object-detection/blob/915b90a5a60a99c00b288c92cab511253c4df87b/Screenshot%202025-12-29%20at%2000.44.24.png)

---

## 📦 Dataset
- **DVXray Dual-View** dataset  
- Paired X-ray images of baggage from two perspectives: **OL (Overhead)** and **SD (Side)**  
- Annotated **bounding boxes** and **class labels**  
- Split into **train, validation, and test sets**  

---

## 🏗️ Model Architecture
- **Backbone**: ResNet18 with `FrozenBatchNorm2d` ❄️  
- **Positional Encoding**: DETR-style 2D sine-cosine 🔣  
- **Encoder**: CVFF Transformer Encoder (GCA + LFS + MAWS + Transformer Blocks) 🔄  
- **Decoder**: DETR-style Transformer Decoder  
- **Heads**:
  - `class_embed` 🎯 for class prediction  
  - `bbox_embed` 📦 for bounding box regression (cxcywh normalized)

---

## ⚙️ Training
- **Losses**:  
  - Classification (CrossEntropy) 🏷️  
  - BBox L1 📏  
  - GIoU 📐  
- **Optimizer**: `AdamW`  
- **Scheduler**: `StepLR`  

**Status**: Fine-tuning in progress on DVXray dual-view dataset 🔥
