# LEGO Brick Detection and Classification

## Overview
This project implements an image processing pipeline for the automatic detection, segmentation, and classification of LEGO bricks using traditional computer vision techniques with the help of OpenCV.
It aims to simulate a factory-like sorting system where LEGO pieces are identified by **color** and **size**, and grouped into predefined kits for verification.

All processing is implemented using an **object-oriented programming (OOP)** approach to ensure modularity and scalability.

### Grade: 16,38
---

## Main Features
- **Image Preprocessing and Calibration**: Undistortion using intrinsic parameters and color space conversions (BGR, RGB, HSV, Gray).  
- **Brick Detection**: HSV color masking, contour extraction, and bounding box computation.  
- **White Brick Segmentation**: Custom detection pipeline using Hough Circles and DBSCAN clustering.  
- **Size Classification**: Based on width/height ratio and area comparison with reference values.  
- **Kit Identification and Fault Detection**: Comparison with predefined kits to detect missing or extra pieces.


---

## Exercises Description

- **Exercise 1 – Calibration**  
  Perform intrinsic and extrinsic calibration of the camera using chessboard images.  
  For the intrinsic part, three calibration attempts (Calib1, Calib2, Calib3) were made using a 12×9 pattern with 15 mm squares, selecting the best result based on reprojection error and parameter stability.  
  For the extrinsic calibration, compute the [R | t] matrix and the pixel-to-millimeter conversion factor using *final setup.png*, ensuring the calibration plane matches the height of the LEGO pieces.

- **Exercise 2 – Isolated Bricks**  
  Process isolated LEGO bricks to identify their color and size, and calculate their average dimensions in both pixels and millimeters.  

- **Exercise 3 – Complete Kits**  
  Detect and classify multiple LEGO bricks within each kit image, group them by color and size, and determine which predefined kit each image represents.  

- **Exercise 4 – Faulty Kits**  
  Analyze kit images that may contain missing or extra pieces. Automatically identify whether each image matches a valid kit or should be classified as faulty, specifying the cause of the discrepancy.  

**Note:** For more detailed information, see the file **Assign1_CV.pdf**.

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
- Afonso Mateus  | afonso.tomas.mateus@gmail.com

- Diogo Oliveira  | odiogo27@gmail.com

---
Developed as part of the first **Computer Vision** course project.
