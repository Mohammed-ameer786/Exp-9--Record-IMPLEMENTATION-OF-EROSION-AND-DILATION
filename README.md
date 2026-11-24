# EX. NO. 09

# IMPLEMENTATION OF EROSION AND DILATION USING OPENCV

## AIM

To write a Python program using OpenCV to perform morphological operations such as Erosion and Dilation on an image.

The program performs the following operations:

- Image Erosion
- Image Dilation

## SOFTWARE REQUIRED

1. Anaconda – Python 3.7
2. Jupyter Notebook / VS Code
3. OpenCV (cv2)
4. NumPy
5. Matplotlib

## ALGORITHM

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Create a blank black image using NumPy.

### Step 3:
Insert text onto the image using OpenCV's text drawing function.

### Step 4:
Display the original image.

### Step 5:
Create a structuring element (kernel) of suitable size.

### Step 6: Image Erosion
- Apply erosion using the created kernel.
- Reduce the thickness of the foreground objects.
- Display the eroded image.

### Step 7: Image Dilation
- Apply dilation using the same kernel.
- Increase the thickness of the foreground objects.
- Display the dilated image.

### Step 8:
Compare the original, eroded, and dilated images.

## PROGRAM

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create a blank black image
img = np.zeros((300, 600), dtype=np.uint8)

# Insert text into the image
cv2.putText(img, "MORPHOLOGY", (50, 180),
             cv2.FONT_HERSHEY_SIMPLEX, 2,
             255, 5, cv2.LINE_AA)

# Display original image
plt.figure(figsize=(8, 4))
plt.imshow(img, cmap="gray")
plt.title("Original Image")
plt.axis("off")
plt.show()

# Create a kernel
kernel = np.ones((5, 5), np.uint8)

# Erosion
eroded = cv2.erode(img, kernel, iterations=1)

# Display eroded image
plt.figure(figsize=(8, 4))
plt.imshow(eroded, cmap="gray")
plt.title("Erosion")
plt.axis("off")
plt.show()

# Dilation
dilated = cv2.dilate(img, kernel, iterations=1)

# Display dilated image
plt.figure(figsize=(8, 4))
plt.imshow(dilated, cmap="gray")
plt.title("Dilation")
plt.axis("off")
plt.show()

# Compare all images
images = [img, eroded, dilated]
titles = ["Original Image", "Erosion", "Dilation"]

plt.figure(figsize=(15, 5))

for i in range(len(images)):
    plt.subplot(1, 3, i + 1)
    plt.imshow(images[i], cmap="gray")
    plt.title(titles[i])
    plt.axis("off")

plt.tight_layout()
plt.show()
```

## DEVELOPED BY

**Name:** Mohammed Ameer F

**Register No:** 212225040248

## OUTPUT

### 1. Original Image
- A black image containing white text is displayed.
<img width="1007" height="457" alt="image" src="https://github.com/user-attachments/assets/47b36c93-dca8-426d-bfa9-d4ac38abfc47" />


  

### 2. Erosion
- The eroded image is displayed.
  <img width="1328" height="332" alt="image" src="https://github.com/user-attachments/assets/41e2785d-65c4-4766-a0ff-9b4fad739884" />


- The thickness of the characters is reduced.
- The boundaries of foreground objects shrink inward.

### 3. Dilation
- The original image is displayed.
  <img width="1007" height="457" alt="image" src="https://github.com/user-attachments/assets/47b36c93-dca8-426d-bfa9-d4ac38abfc47" />

- The dilated image is displayed.
  <img width="1151" height="360" alt="image" src="https://github.com/user-attachments/assets/021d7061-5ea2-48b5-8ac9-cefe9cc586b7" />

- The thickness of the characters increases.
- The boundaries of foreground objects expand outward.

### 4. Comparison of All Operations
- The original, eroded, and dilated images are displayed side by side.
  <img width="1317" height="245" alt="image" src="https://github.com/user-attachments/assets/172913ab-0488-45ac-8b72-3d4bdcf05e70" />

- The effects of erosion and dilation can be compared.

## RESULT

Thus, the morphological operations **Erosion and Dilation** are successfully implemented using OpenCV.
