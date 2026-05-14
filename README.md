# EXP-07    HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform. 

## Software Required:
Anaconda - Python 3.7 

## Algorithm: 
```
Step 1: Import all the necessary modules for the program. 
Step 2: Load an image using imread() from the cv2 module. 
Step 3: Convert the image to grayscale. 
Step 4: Using the Canny operator from cv2, detect the edges of the image.
Step 5: Using the HoughLinesP(), detect line co-ordinates for every point in the images.
Using a for loop, draw the lines on the found coordinates. Display the image.
```

## Name: Oviya N
## Reg No: 212223040140

## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('Qn_7_.jpg')  # Replace 'image.jpg' with your image path
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)  # Canny edge detection with threshold values 50 and 150
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
# Step 5: Using the HoughLinesP(), detect line coordinates for every point in the image
# The parameters of HoughLinesP are: image, resolution, threshold, minLineLength, maxLineGap
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
# Step 6: Using a for loop, draw the lines on the original image using the detected coordinates
# The lines variable contains the endpoints of the detected lines
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)  # Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output:

### Input image:
<img width="476" height="348" alt="image" src="https://github.com/user-attachments/assets/0cfb7c06-c0b8-4aa2-9cff-f9b101e1a7f7" />

### GrayScale image:
<img width="512" height="349" alt="image" src="https://github.com/user-attachments/assets/fd69008c-d7fb-4deb-af51-0d8d2db713d0" />

### Canny Edge Detector:
<img width="459" height="352" alt="image" src="https://github.com/user-attachments/assets/38a3c107-5ec8-4859-917e-a6cba3e82ab2" />

### Result of Hough Transform
<img width="507" height="356" alt="image" src="https://github.com/user-attachments/assets/ce00495a-307d-4044-8ebd-e67b0725939c" />

## Result:
Thus,Python program to detect the lines using Hough Transform has executed successfully.
