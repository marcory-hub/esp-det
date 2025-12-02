# ESP-Detection Training and Quantization for ESP32

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1JMO8i8VDU3ujgr9n1jpZbriLzCD_hiS4?usp=sharing)


This notebook provides a complete workflow for training, exporting, and quantizing object detection models using [esp-detection](https://github.com/espressif/esp-detection), a framework based on Ultralytics YOLO11n optimized for efficient deployment on ESP AI chips (ESP32-P4 and ESP32-S3).

## Overview

ESP-Detection enables deployment of lightweight object detection models on resource-constrained ESP32 microcontrollers. This notebook automates the entire pipeline:

1. **Model Training**: Train ESPDet-Pico models on custom datasets
2. **Model Export**: Convert trained PyTorch models to ONNX format
3. **Quantization**: Generate optimized `.espdl` models for ESP32 deployment

## Requirements

- **Google Colab with GPU** (T4 or better recommended)
- **Python 3.8** virtual environment (required for NumPy 1.24.4 compatibility)
- **Dataset**: YOLO-format dataset uploaded to Google Drive

## Why Python 3.8?

The ESP-Detection repository requires NumPy 1.24.4, which is only compatible with Python 3.8-3.11. Python 3.12+ uses NumPy 2.x by default, causing dependency conflicts. This notebook automatically sets up a Python 3.8 virtual environment to ensure compatibility.

## Workflow

1. **Setup**: Install Python 3.8, create virtual environment, and clone ESP-Detection
2. **Dataset Preparation**: Mount Google Drive and prepare calibration data
3. **Training**: Train ESPDet-Pico model on your custom dataset
4. **Export & Quantization**: Convert to ONNX and quantize for ESP32-S3/P4
5. **Download**: Get the final `.espdl` model file for deployment

## Model Architecture

- **ESPDet-Pico**: Lightweight detection model (~360K parameters)
- **Input Size**: 288×288 pixels (Rect: False) or 160x288 pixels (Rect: True)
- **Output**: Optimized `.espdl` format for ESP-DL inference
