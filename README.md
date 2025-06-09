# Prescription Recognition: Handwritten Medicine Extraction using YOLOv11 and TrOCR

This repository contains a complete deep learning pipeline for recognizing handwritten medicine names from scanned doctor prescriptions. The system integrates YOLOv11 for region detection, TrOCR for handwritten text recognition, and a post-processing step using a curated medicine corpus to ensure reliable and structured output.

---

## Project Objective

The objective of this project is to automate the extraction of medicine names from handwritten prescriptions. The system aims to detect text regions accurately, recognize handwritten content effectively, and correct or validate the recognized text using a structured reference database of medicine names.

---

## Repository Contents

* `Content_Prescription/`
  Contains the core resources:

  * `best.pt`: Pretrained YOLOv11 model weights for medicine detection.
  * `17.jpg`: Sample prescription image for inference.

* `final_prescription_recognition_TrOCR.ipynb`
  Main notebook that implements the entire pipeline from detection to recognition and post-processing.

* `README.md`
  This documentation file describing the methodology, structure, and workflow.

* `LICENSE`
  Licensing information for usage and distribution.

---

## Pipeline Overview

The system is composed of three key stages:

### 1. Text Region Detection using YOLOv11

A custom-trained YOLOv11 object detection model identifies bounding boxes around handwritten medicine names in the prescription image. These regions serve as input for the next recognition step.

### 2. Handwritten Text Recognition using TrOCR

Each cropped region from YOLO is fed into a TrOCR model. TrOCR (Transformers for Optical Character Recognition) is designed for handwritten text and is used here to transcribe the contents of each bounding box into machine-readable text.

### 3. Post-Processing with Medicine Corpus

To improve accuracy and ensure the recognized names correspond to valid medicines, each OCR output is matched against a predefined structured medicine corpus. Fuzzy string matching algorithms are used to find the closest valid match. This step compensates for minor OCR errors and ensures clean, validated output.
The link to access sample corpus csv : https://drive.google.com/file/d/1Dzszq9ERgl62LxVycfQxRJnVkhD81P31/view?usp=sharing

---

## Methodology Summary

* A prescription image is first passed through YOLOv11 to locate handwritten medicine regions.
* Cropped image regions are then sent individually to the TrOCR model for transcription.
* The predicted texts are matched against a curated medicine corpus using approximate string matching to finalize the most probable medicine name.

---

## Features

* Accurate detection of handwritten medicine names using YOLOv11.
* Robust handwritten OCR with transformer-based TrOCR architecture.
* Post-processing with domain-specific corpus to eliminate noise and increase reliability.
* Fully offline, standalone pipeline suitable for production or academic deployment.

---

## Applications

* Prescription digitization for clinics, hospitals, or pharmacies.
* Automated entry of medicine records in healthcare systems.
* Error correction and standardization in medical transcription workflows.

---

## Getting Started

To use this project:

1. Download the files from the `Content_Prescription` directory.
2. Open the `final_prescription_recognition_TrOCR.ipynb` notebook.
3. Follow the workflow within the notebook to load models, process the image, and extract structured medicine names.

---

## License

This repository is provided under the terms outlined in the LICENSE file.


