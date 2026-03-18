
# Edge-Linking-using-Hough-Transformm
## DEVELOPED BY : SHARON STEFFANI.F
## REG NO : 212223110049
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

## Program :

###  Input image and grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("steffy.jpeg", 0)
img_c = cv2.imread("steffy.jpeg", 1)

img_c = cv2.cvtColor(img_c, cv2.COLOR_BGR2RGB)
gray = cv2.cvtColor(img, cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray, (3,3), 0)

plt.figure(figsize=(13,13))

plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")

plt.show()
```

### Canny Edge detector 
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
###  Hough transform
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="1027" height="651" alt="image" src="https://github.com/user-attachments/assets/c71323ef-e80a-4d52-bbf8-3fdbd706fc5a" />

### Canny Edge detector output
<img width="333" height="427" alt="image" src="https://github.com/user-attachments/assets/dfe83095-16bc-44a7-9a59-79f99c4d9495" />

### Display the result of Hough transform
<img width="322" height="430" alt="image" src="https://github.com/user-attachments/assets/db25db14-68d0-4d47-a4df-8571bf18d353" />

