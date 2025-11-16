# Edge-Linking-using-Hough-Transformm
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

## Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('Qn_7_.jpg') 
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


### Input image
<img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/25b924f4-10a0-4663-a867-9be2c95dd2ee" />


### Grayscale image
<img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/98f4d181-ca89-419f-9879-26ec9560324f" />


### Canny Edge detector output
<img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/fb47dc1f-71c7-4cf0-8b88-8d6fdda08b8c" />


### Display the result of Hough transform
<img width="515" height="388" alt="image" src="https://github.com/user-attachments/assets/c965873c-7b20-403c-b9b2-9df7fdab51ef" />


### Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform.
