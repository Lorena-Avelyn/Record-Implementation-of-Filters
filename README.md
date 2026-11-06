# Exp-5- Record-Implementation of Filters

## Experiment Details

- **Name:** Lorena Avelyn R
- **Register Number:** 212224040174

## Aim

To implement filters for smoothing and sharpening images in the spatial domain using OpenCV and Python.

## Software Required

- Anaconda
- Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

**Step 1:** Import the required libraries such as OpenCV, NumPy, and Matplotlib.

**Step 2:** Read the input image using `cv2.imread()`.

**Step 3:** Convert the image from BGR to RGB format using `cv2.cvtColor()`.

**Step 4:** Apply different smoothing filters such as Averaging Filter, Weighted Averaging Filter, Gaussian Filter, and Median Filter.

**Step 5:** Apply sharpening filters using the Laplacian Linear Kernel and Laplacian Operator.

**Step 6:** Display the original and filtered images using `matplotlib.pyplot`.

**Step 7:** End the program.

## Program

### Developed By: Lorena Avelyn R

### Register Number: 212224040174

## 1. Smoothing Filters

### i) Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np

image1 = cv2.imread("Image2.jpg")

image2 = cv2.cvtColor(
    image1, cv2.COLOR_BGR2RGB
)

kernel = np.ones((11, 11), np.float32) / 169

image3 = cv2.filter2D(image2, -1, kernel)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")

plt.show()
```

**Output:**

<img width="828" height="360" alt="image" src="https://github.com/user-attachments/assets/0aa0cd1c-a464-41a3-b9b7-d9c29d3e9eae" />


### ii) Using Weighted Averaging Filter

```python
kernel1 = np.array([
    [1, 2, 1],
    [2, 4, 2],
    [1, 2, 1]
]) / 16

image2 = cv2.cvtColor(
    image1, cv2.COLOR_BGR2RGB
)

image3 = cv2.filter2D(image2, -1, kernel1)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")

plt.show()
```

**Output:**

<img width="743" height="272" alt="image" src="https://github.com/user-attachments/assets/75078cd4-341d-4718-8f4c-4cfcbcf6c071" />


### iii) Using Gaussian Filter

```python
gaussian_blur = cv2.GaussianBlur(
    image2, (33, 33), 0, 0
)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")

plt.show()
```

**Output:**

<img width="685" height="272" alt="image" src="https://github.com/user-attachments/assets/098bd93a-74d2-44b1-bc7e-234444f7dc88" />


### iv) Using Median Filter

```python
median = cv2.medianBlur(image2, 13)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")

plt.show()
```

**Output:**

<img width="830" height="361" alt="image" src="https://github.com/user-attachments/assets/5339f7ca-e0cb-4a86-ad26-912daf238d16" />

## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

```python
kernel2 = np.array([
    [-1, -1, -1],
    [2, -2, 1],
    [2, 1, -1]
])

image3 = cv2.filter2D(image2, -1, kernel2)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")

plt.show()
```

**Output:**

<img width="673" height="277" alt="image" src="https://github.com/user-attachments/assets/d064a7bf-1baa-4565-8624-a39674093a5f" />

### ii) Using Laplacian Operator

```python
laplacian = cv2.Laplacian(
    image2, cv2.CV_64F
)

plt.figure(figsize=(9, 9))

plt.subplot(1, 2, 1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 2, 2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")

plt.show()
```

**Output:**

<img width="673" height="263" alt="image" src="https://github.com/user-attachments/assets/ea224275-fd0e-49e5-b8e9-612fcd7d0b07" />

## Result

Thus, different filters for smoothing and sharpening images in the spatial domain were successfully implemented using OpenCV and Python.

