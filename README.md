# LEGO Brick Detection and Classification

## Overview
This project implements an image processing pipeline for **automatic detection, segmentation, and classification of LEGO bricks** using Python and OpenCV.  
It aims to simulate a factory-like sorting system where LEGO pieces are identified by **color** and **size**, and grouped into predefined kits for verification.

All processing is implemented using an **object-oriented programming (OOP)** approach to ensure modularity and scalability.

### Grade: ??
---

## Main Features
- **Image Preprocessing and Calibration**: Undistortion using intrinsic parameters and color space conversions (BGR, RGB, HSV, Gray).  
- **Brick Detection**: HSV color masking, contour extraction, and bounding box computation.  
- **White Brick Segmentation**: Custom detection pipeline using Hough Circles and DBSCAN clustering.  
- **Size Classification**: Based on width/height ratio and area comparison with reference values.  
- **Kit Identification and Fault Detection**: Comparison with predefined kits to detect missing or extra pieces.

---

## Object-Oriented Structure
| Class | Description |
|-------|--------------|
| `MultiFormat` | Stores multiple color representations of an image. |
| `Pose` | Represents the centroid of a brick. |
| `Dimension`, `UnitAwareDimension` | Manage width, height, and area in pixels and millimeters. |
| `BoxShape` | Computes bounding boxes and geometric features. |
| `LegoBrick` | Represents a single LEGO brick with color and size. |
| `Image` | Main class for detection, mask computation, and visualization. |
| `LegoBrickKit` | Defines and compares kit configurations to detect faults. |

---

## Results
- **Exercise 2:** All color and size classifications were correct. Small area errors were due to calibration height and distortion limitations.  
- **Exercise 3:** All kits correctly identified; 100% accuracy in color and size classification.  
- **Exercise 4:** Faulty and non-faulty kits correctly classified. The only potential issue (white R2x2) was irrelevant, as no predefined kits contained white bricks.

---

## Tools
- Python 3.10  
- OpenCV  
- NumPy, Pandas, Matplotlib  
- scikit-learn  
- Google Colab

---

## Authors
Developed as part of the **Computer Vision** course project.
