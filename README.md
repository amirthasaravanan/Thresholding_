# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.


## Program

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
```python
# Step 2: Read the image and convert to grayscale
image = cv2.imread('flower.png')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
```
```python
# Original # Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')# Original Image

```
```python
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
```
```python
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)

```
```python
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)
```
```python
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')
```
```python
# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')
```
```python
# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')
```
```python
# Show the plot
plt.tight_layout()
plt.show()
```

## Output

### Original Image
<img width="245" height="192" alt="766e45d2-4db6-43df-9248-cb453aea2678" src="https://github.com/user-attachments/assets/08fd3f4b-0a06-4906-aed0-9405620d8f92" />


### Global Thresholding
<img width="245" height="192" alt="e7e79ce5-a8cf-42a0-b2fb-8792e35ab345" src="https://github.com/user-attachments/assets/ab825548-8e08-41c9-8c52-90df0cc31f8d" />


### Adaptive Thresholding

<img width="245" height="192" alt="6abb07a2-76c2-4550-8f08-9ed8e6987070" src="https://github.com/user-attachments/assets/a0917fbe-b561-47a7-82d3-2f184c00a57f" />


### Optimum Global Thesholding using Otsu's Method

<img width="245" height="192" alt="d34e0280-0e60-4c1b-a332-01d7bb89d38d" src="https://github.com/user-attachments/assets/62d76ff7-76cc-4132-9201-1d65d72505e0" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
