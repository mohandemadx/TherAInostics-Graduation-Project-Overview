# Web-Based Deep Learning System for Evaluating Lu-PSMA Therapy Efficacy in Prostate Cancer Using PET/CT

This project presents an **AI-powered theranostics platform** designed to support physicians in evaluating treatment efficacy in **metastatic prostate cancer (mPC)** patients using **Lu-PSMA PET/CT scans**.

> Developed by: Muhammed ElNajjar, Omar Shata, Abduallah Omran, Mohand Attya, Carole Bekhit 
> Under Supervision of: Dr. Ahmed Ehab and Dr. Manar Nasser
> Faculty of Engineering, Cairo University – Department of Systems and Biomedical Engineering

---

## Table of Contents

- [Overview](#overview)
- [System Architecture](#system-architecture)
- [Key Features](#key-features)
- [AI Methodologies](#ai-methodologies)
- [Results](#results)
- [Limitations & Future Work](#limitations--future-work)
- [Demo](#demo)

---

## Overview

Prostate cancer remains a leading cause of cancer mortality in men. **Theranostics**, combining diagnostics and targeted therapy, offers a modern solution. Our platform provides:

-  **AI-driven segmentation & classification**
-  **Longitudinal tracking tools**
-  **Web-based DICOM visualization**
-  **Integration of ResNet & UNet models**

---

##  System Architecture

The platform is composed of:

- **PACS Server** – Secure DICOM storage with compression & backups  
- **Study List** – Interface to search, organize, and classify patient scans  
- **Web-based DICOM Viewer** – Compare axial, sagittal, and coronal views + 3D MIP  
- **AI Module** – 
  - Prostate segmentation (Attention UNet)  
  - Lesion classification (3D ResNet50)  
  - Lesion segmentation (3D UNet w/ CT & PET input)  


---

##  Key Features

-  **Interactive DICOM Viewer**  
  Zoom, pan, crosshair, 3D MIP, segmentation tools, slice comparison, and volume trend analysis.

-  **AI-Powered Tasks**  
  - Prostate segmentation using **Attention UNet**
  - Lesion classification with **3D ResNet**
  - Dual-modality lesion segmentation using **3D UNet**

-  **Longitudinal Tracking**  
  Compare multiple time points, track treatment response via tumor volume and tracer uptake.

---

##  AI Methodologies

###  Prostate Segmentation
- **Dataset**: TCIA – 129 CT studies  
- **Model**: 2D UNet, 3D UNet, Attention UNet  
- **Best Performance**: Attention UNet (Dice = 0.85)  

###  Lesion Classification
- **Dataset**: AutoPET Challenge  
- **Model**: Custom 3D CNN vs ResNet50  
- **Best Performance**: ResNet50 (Accuracy = 73%, Precision = 85%)

###  Lesion Segmentation
- **Input**: Dual-modality (PET + CT)  
- **Model**: 3D UNet  
- **Dice Score**: 0.67 (after post-processing)

---

##  Results

| Task | Model | Score |
|------|--------|--------|
| Prostate Segmentation | Attention UNet | **0.85 Dice** |
| Lesion Segmentation | 3D UNet | **0.67 Dice** |
| Lesion Classification | ResNet50 | **73% Accuracy** |

 **Post-processing improved lesion segmentation by 4%** using body masking.


---

##  Limitations & Future Work

-  Current models trained on **FDG PET/CT** datasets, not PSMA  
-  Plan to retrain on **PSMA-labeled datasets** from Misr Radiology Center  
-  Future improvements in segmentation accuracy with more advanced models

---

## 🎥 Demo

 [Watch the YouTube Demo](https://www.youtube.com/watch?v=smcWChlwsKk&feature=youtu.be)

---
