
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the structuring element

### Step4:
Use Opening operation

### Step5:
Use Closing Operation
 
## Program:

``` 
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Read the color image
input_image_path = 'prema.jpg'
color_image = cv2.imread(input_image_path)

# Convert the color image to grayscale
gray_image = cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)

# Perform edge detection using Canny
edges = cv2.Canny(gray_image, 100, 200)  # you can adjust the thresholds as needed

# Define the kernel size for erosion and dilation
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np.uint8)

# Perform erosion
erosion = cv2.erode(edges, kernel, iterations=1)

# Perform dilation
dilation = cv2.dilate(edges, kernel, iterations=1)

# Perform opening
opening = cv2.morphologyEx(edges, cv2.MORPH_OPEN, kernel)

# Perform closing
closing = cv2.morphologyEx(edges, cv2.MORPH_CLOSE, kernel)

# Display all images
plt.figure(figsize=(15, 10))
plt.subplot(2, 4, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')

plt.subplot(2, 4, 2)
plt.imshow(gray_image, cmap="gray")
plt.title('Black and white Image')
plt.axis('on')

plt.subplot(2, 4, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')

plt.subplot(2, 4, 4)
plt.imshow(erosion, cmap='gray')
plt.title('Erosion')
plt.axis('on')

plt.subplot(2, 4, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')

plt.subplot(2, 4, 6)
plt.imshow(opening, cmap='gray')
plt.title('Opening')
plt.axis('on')

plt.subplot(2, 4, 7)
plt.imshow(closing, cmap='gray')
plt.title('Closing')
plt.axis('on')

plt.show()


```
## Output:
![Screenshot 2024-04-03 103023](https://github.com/premalatha-sureshbabu/OPENING--AND-CLOSING/assets/120620842/5134b9bf-4afe-4d69-af49-86663a9ed427)

## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
