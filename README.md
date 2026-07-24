# Multiclass Tissue Classification and Depth Analysis Framework for Tracking Wound Healing Progress

## 📌 Overview
Over 8 million people suffer from chronic wounds globally, creating a significant healthcare burden with treatment costs ranging from $28.1 billion to $96.8 billion annually. Current manual wound assessment methods are time-consuming, expensive, and subjective. 

This project proposes a two-phase Artificial Intelligence framework to automate wound diagnosis and monitor healing progression over time. Moving beyond traditional static image classification, this framework integrates monocular depth estimation to quantitatively track healing, an approach previously unexplored in existing literature.

## 🚀 Features & Methodology
This system operates in a unified end-to-end pipeline:
* **Phase 1: Wound Classification:** Utilizes a lightweight MobileNetV2 architecture (~3.4M parameters) using transfer learning to categorize wound images. 
* **Phase 2: Depth Estimation & Severity Scoring:** Applies the MiDaS monocular depth estimation model to generate pseudo-depth maps from 2D RGB images. 
* **Healing Analysis:** Maps the extracted structural depth information to a synthetic wound healing progression curve to estimate the healing stage (time step and percentage healed).

## 📊 Dataset
The model was trained and evaluated on the **AZH Wound Dataset**. 
* **Total Images:** 730 wound images in .jpg format.
* **4 Wound Classes:** Diabetic Foot Ulcer (DFU), Pressure Ulcer (PU), Venous Leg Ulcer (VLU), and Surgical Wound (SW).
* **2 Non-Wound Classes:** Background (BG) and Normal Skin (N).

## 🛠️ Tech Stack
* **Language:** Python
* **Deep Learning Framework:** PyTorch, Torchvision
* **Models:** MobileNetV2 (Classification), MiDaS (Depth Estimation)
* **Data Processing & Visualization:** OpenCV, Pandas, NumPy, Matplotlib, Seaborn

## 📈 Results
* **Classification Performance (Phase 1):** The MobileNetV2 model achieved an overall accuracy of **82.05%** and an F1-Score of **0.8206**.
* **Depth Analysis (Phase 2):** Successfully converted 2D visual data into numerical severity scores (e.g., T0 for most severe to Tn for most healed).
* **Pipeline Output:** The final unified function (`analyze_wound`) outputs a 4-panel report containing the original image, depth map, class probabilities, and the wound's position on the healing curve.

## 👥 Contributors
* **Prajwal Meshram**
* **Mubashir Afzal**
