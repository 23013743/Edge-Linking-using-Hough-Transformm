# EX-07 EDGE LINKING HOUGH TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:
```
DEVELOPED BY: VINOLIA ALAINA .R
REGISTER NUMBER: 212224240184
```

### Read image and convert it to grayscale image
```PY
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("VI.jpeg",0)
img_c=cv2.imread("VI.jpeg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
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
### Find the edges in the image using canny detector and display
```PY
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```PY
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```PY
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```PY
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image
<img width="328" height="343" alt="Screenshot 2026-02-23 110733" src="https://github.com/user-attachments/assets/ee7f663f-f08a-4a60-bcbf-037282036952" />
<img width="332" height="334" alt="Screenshot 2026-02-23 110742" src="https://github.com/user-attachments/assets/c6387fe7-b76f-460d-aa28-eadfd62ebff4" />

<br>

### Canny Edge detector output
<img width="389" height="409" alt="f8e523daaeb16f86f25c3c53a7bd59b6_ms5AHC1krSgAAAAASUVORK5CYII=" src="https://github.com/user-attachments/assets/8a56bda2-3d79-4ed6-9bba-e046e3e2dd0a" />

<br>

### Display the result of Hough transform
<img width="389" height="409" alt="8c2ba5b880637679c56d7bbc366e0222_AA0HNMsPm9xAAAAAAElFTkSuQmCC" src="https://github.com/user-attachments/assets/178ccc92-c2c9-49ee-bd04-bb4df37432e5" />

<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
