# A Cascaded YOLOv11 and Attention-Driven U-Net Framework for Autonomous Photovoltaic Hotspot Diagnosis

![Python](https://img.shields.io/badge/Python-3.9%2B-blue)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-orange)
![YOLOv11](https://img.shields.io/badge/YOLO-v11-green)
![Status](https://img.shields.io/badge/Status-In_Development-yellow)

> **Course:** CSE300 Mini Project (Batch M46)
> **Institution:** SASTRA Deemed to be University, Srinivasa Ramanujan Center

## 📌 Abstract
In solar power systems, Photovoltaic (PV) module hot spots dramatically lower efficiency and pose safety hazards. Traditional methods like I-V curve analysis, image-level classification, and simple bounding box detection often struggle to pinpoint the precise location and size of these faults.

This project implements a **Cascaded Deep Learning Framework** that combines the speed of **YOLOv11** with the precision of an **Attention-Driven U-Net**.
1.  **Localization:** YOLOv11 rapidly locates possible hot spot regions and eliminates unimportant background information (roof tiles, vegetation).
2.  **Segmentation:** The cropped regions are fed into a U-Net segmentation network to identify hot spots at the pixel level.

This hybrid approach allows for the precise measurement of fault size, shape, and severity, outperforming standalone detection models in terms of pixel accuracy and Mean Intersection-Over-Union (MIoU).

## 👥 Team Members
| Name | Register No. | Role |
|:---:|:---:|:---:|
| **Ashvathram B** | 227003018 | Developer |
| **Swaminathan S** | 227003148 | Developer |
| **Vishokbadri K** | 227003163 | Developer |

**Project Supervisor:** Dr. Sangeetha J

## 🛠️ Methodology
Our framework addresses the trade-off between real-time speed and segmentation accuracy by using a two-stage pipeline:

### 1. Image Pre-processing
To handle the limited labeled data typical of real-world PV inspections and increase robustness, we apply:
* **Gaussian Blurring:** To reduce thermal noise.
* **Image Sharpening:** To improve edge definition and temperature contrast.

### 2. The Cascade Architecture
* **Stage 1 (Global Detection):** A **YOLOv11** model scans the full thermal image to detect Regions of Interest (RoIs).
* **Stage 2 (Local Segmentation):** The detected RoIs are cropped and passed to an **Attention-Driven U-Net**. This network generates a binary mask to segment the exact shape of the hot spot.

## 📂 Dataset
The model is trained on **Infrared Thermal Images** of photovoltaic modules. The dataset includes classes for:
* `Hotspot`
* `Defective Module`
* `Diode Failure`

📚 References
This project builds upon the following research:M

Liu, B., Chen, L., Sun, K., Wang, X., & Zhao, J. (2024). A Hot Spot Identification Approach for Photovoltaic Module Based on Enhanced U-Net With Squeeze-and-Excitation and VGG19. IEEE Transactions on Instrumentation and Measurement.

Ultralytics YOLOv11 (2024). https://docs.ultralytics.com/models/yolo11/

📝 License
This project is developed for academic purposes at SASTRA Deemed to be University.
