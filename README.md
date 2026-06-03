# Image to Pixels

A foundational computer vision notebook that explores how digital images are represented as pixel arrays. The project loads and displays images from both local files and the **CIFAR-10 dataset**, demonstrating how images are stored, structured, and visualized at the pixel level using NumPy and Matplotlib.

## Overview

This notebook covers the fundamental concept that every image is a 3D NumPy array of pixel values. It walks through loading a local JPEG image, generating random pixel grids, downloading and extracting the CIFAR-10 dataset, and displaying images by decoding their raw binary batch format.

## Dataset

- **Local Image:** User-provided JPEG file
- **CIFAR-10:**
  - Source: [University of Toronto](https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz)
  - 60,000 images across 10 classes (32×32 pixels, RGB)
  - Downloaded and extracted programmatically within the notebook

## Project Structure

```
Image-To-Pixels-Code-main/
└── ImgToPixel.ipynb    # Main Jupyter Notebook
```

## Workflow

### 1. Local Image Loading & Display
- Load a local JPEG image using `matplotlib.image.imread`
- Display image with `plt.imshow`, axes hidden

### 2. Random Pixel Grid Generation
- Generate 3 random `32×32×3` NumPy arrays
- Display as a 1×3 subplot grid to demonstrate raw pixel structure

### 3. CIFAR-10 Dataset Download & Extraction
- Download `cifar-10-python.tar.gz` from the official source using `urllib.request`
- Extract the archive using Python's `tarfile` module

### 4. CIFAR-10 Batch Loading & Visualization
- Load `data_batch_1` using `pickle`
- Reshape raw data from `(N, 3072)` flat arrays to `(N, 32, 32, 3)` image tensors
- Transpose channel order from `(N, C, H, W)` → `(N, H, W, C)` for Matplotlib compatibility
- Display the first 5 CIFAR-10 images in a row

## Requirements

- Python 3.x
- Jupyter Notebook or JupyterLab
- numpy
- matplotlib

Both libraries are part of the standard scientific Python stack. Install with:

```bash
pip install numpy matplotlib jupyter
```

## Usage

```bash
git clone https://github.com/your-username/Image-To-Pixels-Code.git
cd Image-To-Pixels-Code
jupyter notebook ImgToPixel.ipynb
```

Run cells in order. The CIFAR-10 dataset is downloaded automatically. For the local image cell, update the file path to point to an image on your machine.

## Outputs

- Displayed local image (axes-off)
- Grid of 3 randomly generated pixel images
- First 5 CIFAR-10 images rendered from raw binary batch data

## Key Concepts

| Concept | Purpose |
|---|---|
| Image as NumPy Array | Every image is a 3D array of shape (H, W, C) with pixel values 0–255 |
| `mpimg.imread` | Reads image files into NumPy arrays for processing and display |
| Random Pixel Grid | Demonstrates that images are just arrays of floating-point values |
| CIFAR-10 Batch Format | Images stored as flat 3072-element arrays, must be reshaped and transposed |
| `pickle.load` | Deserializes binary CIFAR-10 batch files into Python dictionaries |
