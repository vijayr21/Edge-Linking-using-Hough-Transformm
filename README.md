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

### Code :
### Developed by:   VIJAY R
### Register Number: 212223240178

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

for line in lines:
    x1, y1, x2, y2 = line[0] 
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

## Output
### Input image
![image](https://github.com/user-attachments/assets/3a62942b-2fd4-4f90-9901-e13c653aae5b)


### Grayscale image
![image](https://github.com/user-attachments/assets/85bd4c1c-3e4f-48d8-b1b5-e8fddc8b0bd4)


### Canny Edge detector output
![image](https://github.com/user-attachments/assets/69044d6b-5e27-4212-a049-8bb379300f13)


### Display the result of Hough transform
![image](https://github.com/user-attachments/assets/f6b42423-2d97-415f-9c8a-fb49c9dc01a8)



## Result

Thus,The Python program to detect the lines using Hough Transform run successfully.
