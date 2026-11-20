# Edge-Linking-using-Hough-Transformm
## NAME : POOJA SRI P
## REG NO : 212224230197
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program
```.py

import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('pic.jpeg')

gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Input Image")
plt.axis('off')

plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')

edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')


```
## Output

### Input image and grayscale image

<img width="483" height="516" alt="image" src="https://github.com/user-attachments/assets/59f61992-2477-4c5f-a6cc-7ee3809e416f" />

<img width="436" height="512" alt="image" src="https://github.com/user-attachments/assets/89b0ad29-5e11-41b6-b2aa-d43300399b51" />



### Canny Edge detector output

<img width="503" height="520" alt="image" src="https://github.com/user-attachments/assets/ffbfb43e-1ec0-4a35-92af-ac709857dd78" />


### Display the result of Hough transform

<img width="660" height="692" alt="image" src="https://github.com/user-attachments/assets/dd6c4f9b-1343-4007-85f1-0bf2dc5da073" />



## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.



