# Ex 8 THRESHOLDING
## Name: BALA MURUGAN S
## Register No: 212223230027

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
#Developed by : ALDRIN.S
#Register No: 212223240005

# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt



# Read the Image and convert to grayscale
image = cv2.imread('dog.png')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')



# Use Global thresholding to segment the image
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)



# Use Adaptive thresholding to segment the image

adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)


# Use Otsu's method to segment the image 

_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results
# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()


```
## Output

### Original Image
<img width="206" height="267" alt="Screenshot 2026-03-26 232728" src="https://github.com/user-attachments/assets/3c4c33fa-251d-413f-830b-64ee34bf61e2" />


### Global Thresholding
<img width="229" height="288" alt="Screenshot 2026-03-26 232805" src="https://github.com/user-attachments/assets/1321f734-0f77-4999-8c5f-0b82e8ead999" />


### Adaptive Thresholding

<img width="246" height="281" alt="Screenshot 2026-03-26 232836" src="https://github.com/user-attachments/assets/68d6d9c1-b8af-47f6-a2b6-54021a70a9d1" />

### Optimum Global Thesholding using Otsu's Method

<img width="217" height="286" alt="image" src="https://github.com/user-attachments/assets/9a6edab6-4884-4d05-aa45-fadc127c29ca" />


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
