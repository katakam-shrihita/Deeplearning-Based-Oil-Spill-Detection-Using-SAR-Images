# Deeplearning-Based-Oil-Spill-Detection-Using-SAR-Images

# Deep Learning-Based Oil Spill Detection Using SAR Images

## 📌 Overview

This repository presents a deep learning framework for **oil spill detection and semantic segmentation** using Sentinel-1 Synthetic Aperture Radar (SAR) imagery. The project focuses on distinguishing true oil spills from visually similar look-alike phenomena such as low-wind zones, biogenic films, and sea clutter using encoder–decoder segmentation architectures.

The work evaluates multiple baseline models and proposes an enhanced attention-based U-Net variant for improved boundary delineation and segmentation accuracy.

---

## 🛰️ Dataset

* **Dataset:** M4D Sentinel-1 SAR Oil Spill Dataset
* **Source:** European Space Agency (ESA) – Copernicus Open Access Hub
* **Total Images:** 1,112

  * Training & Validation: 1,002
  * Testing: 110

### Classes

* Sea Surface
* Oil Spill
* Look-Alike Phenomena
* Ships
* Land

Preprocessing steps include:

* Radiometric calibration
* Speckle noise filtering
* Cropping
* Resizing to 256×256
* Mask generation

---

## 🧠 Implemented Models

The repository includes in-house implementations of the following segmentation architectures:

* **Base U-Net**
* **PSPNet**
* **LinkNet**
* **SegNet**
* **Proposed Attention-Based U-Net**

Each model is trained and evaluated on the same SAR dataset for fair comparison.

---

## 🚀 Proposed Method

The proposed model enhances the standard U-Net architecture using:

* Convolutional Block Attention Module (CBAM)
* Channel Attention
* Spatial Attention
* Boundary-aware learning
* Composite loss function

### Loss Components

* Categorical Cross-Entropy
* Jaccard (IoU) Loss
* Tversky Loss
* Boundary Loss

This combination improves:

* Spill boundary delineation
* Class imbalance handling
* Region overlap accuracy

---

## 📊 Evaluation Metrics

Performance is evaluated using:

* Overall Accuracy
* Precision
* Recall
* F1-Score
* Mean IoU

---

## 📈 Results Summary

| Model              | Accuracy   | Precision  | mIoU       | F1-Score   |
| ------------------ | ---------- | ---------- | ---------- | ---------- |
| Base UNet          | 93.1%      | 93.6%      | 54.6%      | 93.3%      |
| PSPNet             | 88.6%      | 92.5%      | 44.0%      | 90.01%     |
| LinkNet            | 93.6%      | 94.0%      | 55.39%     | 93.8%      |
| SegNet             | 92.7%      | 93.0%      | 48.69%     | 92.8%      |
| **Proposed Model** | **96.19%** | **95.00%** | **62.35%** | **95.94%** |

The proposed model demonstrates superior segmentation accuracy and robustness.

---

## 🗂️ Repository Structure

```
├── Base_unet.ipynb        → Baseline U-Net implementation
├── PSPNet_1.ipynb        → PSPNet model
├── LinkNet_1.ipynb       → LinkNet model
├── Segnet_1.ipynb        → SegNet model
├── proposed.ipynb        → Proposed Attention U-Net
└── README.md             → Project documentation
```

---

## ⚙️ Environment & Requirements

* Python 3.x
* TensorFlow / Keras
* NumPy
* OpenCV
* Matplotlib
* Scikit-learn

Install dependencies:

```bash
pip install tensorflow numpy opencv-python matplotlib scikit-learn
```

---

## 🖥️ Training Setup

* Platform: Google Colab
* GPU: NVIDIA Tesla T4
* Framework: TensorFlow (Keras API)

---

## 📷 Qualitative Outputs

The models are evaluated visually using segmentation masks comparing predicted oil spill regions against ground truth annotations.

---

## 🔬 Research Contribution

This work contributes:

* Attention-enhanced segmentation for SAR oil spills
* Boundary-aware optimization
* Multi-class spill vs look-alike discrimination
* Comparative benchmarking with baseline models

---

## 📜 License

This project is intended for academic and research purposes.

---

## 🤝 Acknowledgment

Dataset provided by ESA Copernicus Program.
Research conducted for oil spill monitoring and marine environmental protection.

---

