# EDGE--LINKING-HOUGH-TRANSFORM
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.
<br>

### Step2:
Find the edges in the image using canny detector and display.
<br>

### Step3:
Detect points that form a line using HoughLinesP.
<br>

### Step4:
Draw lines on the image.
<br>

### Step5:
Display the result.
<br>


## Program:
```
DEVELOPED BY : ALDRIN LIJO J E
REG NO : 212222240007
```


# Read image and convert it to grayscale image
```
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("dog.jpeg",0)
img_c=cv2.imread("dog.jpeg",1)
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



# Find the edges in the image using canny detector and display
```
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```



# Detect points that form a line using HoughLinesP
```
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```



# Draw lines on the image
```
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```



# Display the result
```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```





## Output

### Input image and grayscale image


![download](https://github.com/aldrinlijo04/EDGE--LINKING-HOUGH-TRANSFORM/assets/118544279/9118496b-40b5-4d7f-80e7-d8a889933426)


<br>

### Canny Edge detector output


![download](https://github.com/aldrinlijo04/EDGE--LINKING-HOUGH-TRANSFORM/assets/118544279/93550050-6567-48ba-91dc-4954442ad5f1)


<br>


### Display the result of Hough transform

![download](https://github.com/aldrinlijo04/EDGE--LINKING-HOUGH-TRANSFORM/assets/118544279/4285f413-aca3-49a9-81b6-e30ef1975b1d)



<br>



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
