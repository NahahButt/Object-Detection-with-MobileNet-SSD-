# Object Detection with MobileNet-SSD 🖼️🔍

![Python](https://img.shields.io/badge/Python-3.10-blue)
![OpenCV](https://img.shields.io/badge/OpenCV-4.x-green)
![License](https://img.shields.io/badge/License-MIT-yellow)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

Real-time-capable object detection pipeline built with OpenCV's DNN module and a pre-trained **MobileNet-SSD (Caffe)** model.

> **DecodeLabs AI Internship — Image/Text Recognition (Basic), Path 2**

---

![Detection Output](assets/final_annotated_output.jpg)

## 📑 Table of Contents

- [Overview](#overview)
- [Pipeline](#pipeline)
- [Tech Stack](#tech-stack)
- [Features](#features)
- [Sample Result](#sample-result)
- [Validation Summary](#validation-summary)
- [Why MobileNet-SSD?](#why-mobilenet-ssd)
- [Example Outputs](#example-outputs)
- [Getting Started](#getting-started)
- [Project Structure](#project-structure)
- [Model Details](#model-details)
- [Possible Extensions](#possible-extensions)
- [Future Work](#future-work)
- [Author](#author)
- [License](#license)
- [Acknowledgments](#acknowledgments)

---

# Overview

This project performs object detection using **MobileNet-SSD** with OpenCV's DNN module.

The pipeline:

- Accepts an input image
- Performs diagnostic preprocessing
- Detects objects using MobileNet-SSD
- Applies confidence filtering
- Removes duplicate detections using Non-Max Suppression (NMS)
- Saves annotated images
- Exports structured JSON and CSV results

The notebook also includes an **interactive Plotly dashboard** and a conceptual **active-learning feedback loop** showing how low-confidence predictions could be reviewed and incorporated into future model retraining.

---

# Pipeline

```
Input Image
      │
      ▼
Grayscale
      │
      ▼
Gaussian Blur
      │
      ▼
Otsu Threshold
      │
      ▼
MobileNet-SSD Detection
      │
      ▼
Confidence Filter (≥80%)
      │
      ▼
Non-Max Suppression
      │
      ▼
Annotated Image + JSON + CSV + Validation Report
```

---

# Tech Stack

- Python
- OpenCV
- MobileNet-SSD
- Caffe
- NumPy
- Pandas
- Plotly
- Google Colab

---

# Features

- ✅ MobileNet-SSD (Caffe)
- ✅ Fast CPU inference
- ✅ Diagnostic preprocessing
- ✅ Confidence threshold (80%)
- ✅ Non-Max Suppression (NMS)
- ✅ JSON export
- ✅ CSV export
- ✅ Plotly dashboard
- ✅ Active-learning demonstration
- ✅ Automated validation report

---

# Sample Result

| Label | Confidence | Bounding Box |
|------|-----------|---------------------------|
| bicycle | 99.76% | (81,132,571,422) |
| car | 99.36% | (460,71,687,172) |
| dog | 96.70% | (138,209,326,537) |

### Detection Output

![Detection Output](assets/final_annotated_output.jpg)

Full results:

- `results/results.json`
- `results/results.csv`

---

# Validation Summary

✅ Image Loaded Successfully

✅ Model Loaded Successfully

✅ Objects Detected

✅ Confidence Threshold Applied (80%)

✅ Results Exported Successfully

---

# Why MobileNet-SSD?

MobileNet-SSD provides an excellent balance between **speed** and **accuracy**, making it ideal for lightweight CPU-based object detection while maintaining real-time performance.

---

# Example Outputs

## JSON

```json
[
  {
    "label": "dog",
    "confidence": 96.7,
    "box": [138,209,326,537]
  }
]
```

## CSV

```text
label,confidence,x1,y1,x2,y2
dog,96.7,138,209,326,537
```

---

# Getting Started

## Option A — Google Colab

Open:

```
notebooks/Project4_Object_Detection.ipynb
```

Run:

```
Runtime → Run All
```

Model weights and sample image are downloaded automatically.

---

## Option B — Local Installation

```bash
git clone https://github.com/<your-username>/<repo-name>.git

cd <repo-name>

pip install -r requirements.txt

jupyter notebook notebooks/Project4_Object_Detection.ipynb
```

---

# Requirements

- Python 3.10+
- OpenCV
- NumPy
- Pandas
- Plotly
- Jupyter Notebook

---

# Project Structure

```
.
├── notebooks/
│   └── Project4_Object_Detection.ipynb
│
├── assets/
│   └── final_annotated_output.jpg
│
├── results/
│   ├── results.json
│   └── results.csv
│
├── requirements.txt
├── README.md
└── LICENSE
```

> Model weights are downloaded automatically during notebook execution and are excluded via `.gitignore`.

---

# Model Details

| Property | Value |
|-----------|------------------------------|
| Model | MobileNet-SSD |
| Framework | Caffe |
| Classes | 20 Pascal VOC |
| Confidence Threshold | 80% |
| NMS IoU | 0.40 |

---

# Outputs

Running the notebook generates:

- Annotated detection image
- JSON results
- CSV results
- Validation report

---

# Possible Extensions

- YOLOv8 Integration
- YOLO-NAS
- Batch Image Processing
- mAP Evaluation
- Annotation Tool Integration

---

# Future Work

- Live Webcam Detection
- Video Object Detection
- Streamlit Web Application
- Docker Deployment
- ONNX Optimization

---

# Author

**Nahah Butt**

Computer Science Student

**DecodeLabs AI Internship**

---

# License

This project is licensed under the **MIT License**.

---

# Acknowledgments

- MobileNet-SSD Caffe weights:
  https://github.com/robmarkcole/object-detection-app

- Sample image:
  https://github.com/pjreddie/darknet
