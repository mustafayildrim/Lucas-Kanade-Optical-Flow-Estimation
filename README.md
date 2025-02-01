# Optical Flow Estimation

## Description

This project implements the **Lucas-Kanade optical flow algorithm** to compute **pixel-wise motion** between two sequential images. Optical flow fields are computed for three image sets: **Synth, Sphere, and Corridor**. The input images are first converted to grayscale and normalized to the range **[0,1]** before processing.

## Features

- **Lucas-Kanade Optical Flow Estimation**
- **Computation of Spatial and Temporal Derivatives**
- **Gaussian Filtering for Noise Reduction**
- **Flow Vector Calculation using Matrix Inversion**
- **Binary Flow Mask Generation**
- **Visualization of Optical Flow Maps**

## Technologies Used

- **Python**
- **NumPy**
- **Matplotlib**
- **Torch**
- **Kornia**
- **OpenCV**

## Installation

```bash
pip install numpy matplotlib torch kornia opencv-python
```

## Project Tasks

### **Step 1: Preprocess Images**

- Convert images to grayscale.
- Normalize intensity values to the range **[0,1]**.

### **Step 2: Compute Spatial and Temporal Derivatives**

- Compute **Ix** and **Iy** using a **central differences filter**.
- Compute **It** by subtracting the first image from the second.

### **Step 3: Estimate Optical Flow**

- Construct the **2×2 structure tensor matrix** for each pixel.
- Solve the **Lucas-Kanade equation** using matrix inversion.
- Apply a threshold to determine reliable flow values.

### **Step 4: Visualize Optical Flow**

- Generate and display **horizontal (u) and vertical (v) flow components**.
- Create a **binary mask** indicating valid flow regions.
- Use **flowToColor** to visualize flow direction and magnitude.

## Visualizations

- **Binary Flow Mask:** Display regions where motion is detected.
- **Optical Flow Maps:** Show horizontal and vertical flow components.


- **Thresholding Effects:** Show variations in flow detection based on parameter tuning.

