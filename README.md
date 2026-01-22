# Camera Calibration and 2D Dimension Estimation

**Course:** CSc 8830 – Computer Vision  
**Author:** Bala  Pavani Lakshmi Priya Koppuravuri

---

## 📌 Assignment Overview

This Assignment implements a **two-stage computer vision pipeline** for camera calibration and real-world dimension estimation using a smartphone camera.

### Pipeline Stages
- **Step 1:** Intrinsic camera calibration to determine focal length and optical center  
- **Step 2 & 3:** Estimation and validation of real-world object dimensions using perspective projection equations  

---

## 📁 Repository Structure

```
├── Balapavani_Camera_Calibration_Validation.ipynb     # Code snippets for calibration and validation
├── camera_params.npz     # Saved camera matrix and distortion coefficients
├── images/               # Calibration images (17) and validation image
└── README.md             # Project documentation
```

---

## ⚙️ Technical Details

### Step 1: Intrinsic Camera Calibration

The calibration process follows **Zhang’s Method**, using multiple images of a **9×6 internal corner chessboard pattern**.

- **Corner Detection:**  
  - `cv2.findChessboardCorners`  
  - `cv2.cornerSubPix` for sub-pixel refinement  

- **Calibration Output:**  
  - Intrinsic camera matrix **K**  
  - Distortion coefficients  
  - Estimated focal length: **fₓ ≈ 4672.08 pixels**

---

### Step 2: Perspective Projection

Real-world object dimensions are estimated using the **Pinhole Camera Model** and the principle of **similar triangles**.

**Formula:**

H = (f × h) / Z

Where:
- **h** = Pixel height of the object in the image  
- **Z** = Distance from camera to object (3048 mm)  
- **f** = Calibrated focal length (4672.08 px)

---

### Step 3: Experimental Validation

- Plushie imaged at **3.048 meters (10 feet)**
- Estimated height compared with manual measurements and image upload
- Error margins used to validate accuracy

---

## 🚀 Setup and Execution

### Prerequisites

```bash
pip install opencv-python numpy pillow-heif
```

### Running the Scripts

**Camera Calibration**
```bash
python calibrate.py
```

**Object Measurement**
```bash
python measure_object.py
```

---

## ✅ Results

- Accurate intrinsic calibration
- Successful real-world dimension estimation
- Close agreement with manual measurements and image upload which gave same output 

---

