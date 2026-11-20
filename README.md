# EXP 08 - Record-THRESHOLDING
## NAME : RAGASUDHA R
## REG NO :212224230215

## AIM

To segment an input image using Global Thresholding, Adaptive Thresholding, and Otsu’s Thresholding method in OpenCV.

## PROCEDURE

1. Start the program and import the required libraries (cv2, numpy, and matplotlib.pyplot).
2. Load the input image using cv2.imread() and convert it into a grayscale image using cv2.cvtColor().
3. Apply Global Thresholding using cv2.threshold() with a threshold value of 127.
4. Apply Adaptive Thresholding using cv2.adaptiveThreshold() with the Gaussian method.
5. Apply Otsu’s Thresholding using cv2.threshold() with the Otsu method.
6. Display the original image, Global Thresholding, Adaptive Thresholding, and Otsu’s Method outputs using matplotlib.pyplot.
7. Stop the program.

## CODE

```PYTHON
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Read the image and convert to grayscale
image = cv2.imread('photo.jpeg')  # Replace with your image file path
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)  # Convert to grayscale
# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert from BGR to RGB for display
plt.title("Original Image")
plt.axis('off')
# Step 3: Use Global Thresholding to segment the image
# Apply global thresholding with a threshold value of 127
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)
# Step 4: Use Adaptive Thresholding to segment the image
# Apply adaptive thresholding using Gaussian method
adaptive_thresholded = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C, cv2.THRESH_BINARY, 11, 2)
# Step 5: Use Otsu's method to segment the image
# Apply Otsu's method for optimal thresholding
_, otsu_thresholded = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)



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

## OUTPUT
<img width="752" height="310" alt="image" src="https://github.com/user-attachments/assets/81c28936-9d96-4a12-810a-31b114946dc7" />
<img width="707" height="587" alt="image" src="https://github.com/user-attachments/assets/bc816ef8-f307-4f2b-9299-6d8b05f8e8fb" />



## RESULT

The input image is successfully segmented using Global, Adaptive, and Otsu’s Thresholding methods. The original image and the three thresholded outputs are displayed successfully.
