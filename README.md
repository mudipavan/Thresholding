# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image

### Step4:
Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image.

### Step6:
Display the results.


## Program

```python
NAME:pavan mudi
REG NO: 212221230067

# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2



# Read the Image and convert to grayscale

image = cv2.imread("shinchan.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("shinchan.jpg",0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)


# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()



```
## Output

### Original Image

![dip p 9-1](https://user-images.githubusercontent.com/94828517/234795757-602544d8-aa94-46c5-9774-5dc9e27075d4.jpg)


### Global Thresholding


![dip p 9-2](https://user-images.githubusercontent.com/94828517/234795979-83252ffc-cec3-4e2d-b429-9f1620352395.jpg)
![dip p 9-3](https://user-images.githubusercontent.com/94828517/234795962-6c82e0a8-1dca-4214-96fa-7dda5890c7ac.jpg)
![dip p 9-4](https://user-images.githubusercontent.com/94828517/234795943-85c025c1-4433-4380-a408-a3f40a1184cb.jpg)
![dip p 9-5](https://user-images.githubusercontent.com/94828517/234796227-4a5b0ec7-d593-4045-85bf-1ec2e2dc611a.jpg)
![dip p 9-6](https://user-images.githubusercontent.com/94828517/234795908-0d165538-8083-4171-a588-706a0fb36d4d.jpg)


### Adaptive Thresholding

![dip p 9-8](https://user-images.githubusercontent.com/94828517/234796342-09e57374-8340-4181-b937-af34628b531e.jpg)
![dip p 9-9](https://user-images.githubusercontent.com/94828517/234796312-4d609e45-28f8-4312-a9a1-dc9574b9f8cb.jpg)


### Optimum Global Thesholding using Otsu's Method

![dip p 9-7](https://user-images.githubusercontent.com/94828517/234796537-3e6eb0ba-73ba-4d2d-9646-17f99add4275.jpg)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

