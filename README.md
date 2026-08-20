# EXP-7-Detect-the-lines-using-Hough-Transform
## Lane Detection
## Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

## Learning Objective
Understand each stage of image processing
Learn how to build a complete computer vision pipeline
Practice writing code in guided sections
Important Instruction: 👉 Write code ONLY in places marked as # Your Code Here 👉 Do NOT modify any other part of the code

## Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
## Algorithm 

Step1:
Import all the necessary modules for the program.

Step2:
Load a image using imread() from cv2 module.

Step3:
Convert the image to grayscale.

Step4:
Using Canny operator from cv2,detect the edges of the image.

Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
# Step 2: Load the image using imread() from cv2 module
image = cv2.imread('thala.jpg')  # Replace 'image.jpg' with your image path
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

## Expected Output
<img width="830" height="545" alt="image" src="https://github.com/user-attachments/assets/0c37d265-133b-4d0f-820f-3c01f68f94dc" />
<img width="764" height="560" alt="image" src="https://github.com/user-attachments/assets/e93b6f7b-15da-48c9-beff-b4d66182236a" />
<img width="783" height="542" alt="image" src="https://github.com/user-attachments/assets/ad282ad3-7bce-4aa3-ac8e-018e1f2352e2" />
<img width="800" height="561" alt="image" src="https://github.com/user-attachments/assets/c3c04066-c3a8-4f5d-ac76-a293b4af5b1c" />


## Result
Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

Developed By
Name: SARAVANAN K
Register No: 212225040387
