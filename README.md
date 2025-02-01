# Lucas-Kanade Optical Flow Estimation

## Description

This project implements the **Lucas-Kanade optical flow algorithm** to estimate **pixel-wise motion** between two sequential images. Optical flow fields are computed for three datasets: **Synth, Sphere, and Corridor**. The algorithm first converts images to grayscale and normalizes them to the range **[0,1]** before processing.

## Features

- **Lucas-Kanade Optical Flow Estimation**
- **Spatial and Temporal Gradient Computation**
- **Gaussian Filtering for Noise Reduction**
- **Flow Vector Calculation using the Structure Tensor Matrix**
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

### **Step 1: Preprocessing**

- Convert input images to **grayscale** and normalize pixel values to **[0,1]**.

### **Step 2: Computing Spatial and Temporal Derivatives**

- Compute **Ix** and **Iy** using a **central differences filter**.
- Compute **It** by applying a **Gaussian blur** to both images and subtracting the first from the second.

### **Step 3: Estimating Optical Flow**

- Initialize **u, v**, and a **binary flow map**.
- Extract a **local gradient window** centered at each pixel.
- Compute **IxIx, IyIy, IxIy, IxIt, IyIt** over the window.
- Construct the **structure tensor matrix (ATA)** and solve for **(u, v)** using the **pseudoinverse**.
- Apply a threshold to ensure stable optical flow estimation based on **eigenvalues of ATA**.

### **Step 4: Visualizing Optical Flow**

- Display **horizontal (u) and vertical (v) flow components**.
- Generate a **binary mask** indicating valid flow regions.
- Use **flowToColor** to visualize flow direction and magnitude.

## Visualizations

- **Binary Flow Mask:** Displays regions where motion is detected.
- **Optical Flow Maps:** Shows horizontal and vertical flow components.
- **Thresholding Effects:** Displays variations in flow detection based on parameter tuning.

