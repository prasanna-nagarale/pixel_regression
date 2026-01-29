# ML Assignment – Supervised Regression using Deep Learning

## Problem Statement
The goal of this assignment is to predict the coordinates `(x, y)` of a pixel with intensity value **255** in a **50×50 grayscale image**, where all other pixels have value **0**.

The active pixel location is randomly assigned for each image. The task is therefore framed as a **supervised regression problem** using deep learning.

---

## Approach Overview
A Convolutional Neural Network (CNN) is trained to directly regress the pixel coordinates.

Pipeline:

1. Generate synthetic grayscale images of size 50×50.
2. Randomly assign one pixel value to 255.
3. Normalize image and coordinate values.
4. Train CNN to predict normalized `(x, y)` coordinates.
5. Evaluate model using MAE and pixel distance error.
6. Visualize predictions against ground truth.

---

## Dataset Generation Rationale
Synthetic data generation is ideal for this problem because:

- Only one pixel is active per image.
- Infinite data can be generated easily.
- Random pixel placement ensures uniform learning.
- No dataset bias is introduced.

Images are normalized to `[0,1]` for stable training, and coordinates are scaled between `[0,1]` to simplify regression.

---

## Model Architecture
A CNN is used due to its ability to learn spatial patterns.

Model pipeline:

- Convolution layers extract spatial features.
- Pooling reduces dimensionality.
- Fully connected layers predict `(x, y)` coordinates.
- Sigmoid output ensures normalized predictions.

---

## Evaluation Metrics
Two evaluation metrics are used:

### 1. Mean Absolute Error (MAE)
Measures coordinate regression error.

### 2. Pixel Distance Error
Measures distance in pixels between prediction and true location:


This gives intuitive spatial error measurement.

---

## Training Outputs
The notebook includes:

- Training & validation loss curves
- MAE curves
- Ground truth vs predicted coordinate visualization
- Pixel error distribution histogram

---

## Results Summary
The CNN learns pixel locations effectively and achieves very low prediction error.

Most predictions fall within a few pixels of ground truth.

---

## Repository Structure
.
├── Ml_assignment_DeepEdge.ipynb
├── requirements.txt
└── README.md


---

## Installation
Install required packages:

```bash
pip install -r requirements.txt

Running the Notebook

Open the notebook:

jupyter notebook


and run all cells sequentially.

Possible Improvements



Conclusion

The assignment demonstrates how deep learning can solve regression tasks on spatial image data effectively using CNNs.

The approach meets assignment requirements and provides interpretable evaluation results.