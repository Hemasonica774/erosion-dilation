# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the image

### Step2:
Read the colour image and convert it into grayscale

### Step3:
Perform edge detection using canny

### Step4:
Define the kernel size for erosion and dilation

### Step5:
Display all images

## Program:

### Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
### Create the Text using cv2.putText
```
input_image_path = 'hema.jpg'
color_image = cv2.imread(input_image_path)
gray_image=cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 100, 200) # you can adjust the thresholds as needed
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np. uint8)
erosion = cv2.erode(edges, kernel, iterations=1)
dilation = cv2.dilate(edges, kernel, iterations=1)
```
### Create the structuring element
```
plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap="gray")
plt.title('Black and white Image')
plt.axis('on')
plt.subplot(2, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')
```
### Erode the image
```
plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap = 'gray')
plt.title('Erosion')
plt.axis('on')
```
### Dilate the image
```
plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')
plt.show()

```
## Output:

### Display the input Image

![Screenshot 2024-04-04 194828](https://github.com/Hemasonica774/erosion-dilation/assets/118361409/f0fc23dc-50ab-4f5f-b9c5-e028e2973c18)

### Display the Eroded Image

![Screenshot 2024-04-04 194835](https://github.com/Hemasonica774/erosion-dilation/assets/118361409/4d39a760-dcd1-4c26-b7de-dfdde3e73568)

### Display the Dilated Image

![Screenshot 2024-04-04 194840](https://github.com/Hemasonica774/erosion-dilation/assets/118361409/40d1612e-f5ff-4760-9e1a-e3efeb1e9406)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
