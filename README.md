# IMAGE-TRANSFORMATIONS
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

Translation moves the image along the x or y-axis.

Scaling resizes the image by scaling factors.

Shearing distorts the image along one axis.

Reflection flips the image horizontally or vertically.

Rotation rotates the image by a given angle.

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.

## Program:
### Developed By: SRINITHI V
### Register Number: 212222110046
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('harry.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 
plt.figure(figsize=(7,3))
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis('off')
```

### Output:
### i)Image Translation
```py
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]]) 
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.figure(figsize=(7,3))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```

### Output:
### ii) Image Scaling
```py
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.figure(figsize=(7,3))
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```

### Output:
### iii)Image shearing
```py
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) 
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.figure(figsize=(7,3))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```

### Output:
### iv)Image Reflection
```py
reflected_image = cv2.flip(image_rgb, 1)  
plt.figure(figsize=(7,3))
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```

### Output:
### v)Image Rotation
```py
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 150, 1) 
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.figure(figsize=(7,3))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```

### Output:
### vi)Image Cropping
```py
cropped_image = image_rgb[50:300, 100:400]  
plt.figure(figsize=(7, 3))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```

### Output:
## Result: 
Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
