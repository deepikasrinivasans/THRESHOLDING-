# EX-08 THRESHOLDING
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
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
Use Otsu's method to segment the image and display the results.
## Program
```
DEVELOPED BY: DEEPIKA S
REGISTER NO: 212222230028
```
### Load the necessary packages
```
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
### Read the Image and convert to grayscale
```
image = cv2.imread("thresholding.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("thresholding.jpg",0)
```
### Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
### Use Adaptive thresholding to segment the image
```
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
### Use Otsu's method to segment the image 
```
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
### Display the results
```
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
![1d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/345c1aa1-5907-4946-9833-6cd9b165b6d9)
### Global Thresholding
![2d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/d7aa9ee3-f19a-42d6-affc-2c6cfb16d30f)
![3d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/1e026a1e-ebf1-45b5-a6d3-2bbe85403cb5)
![4d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/bb1750de-b9aa-4268-8605-81b1ad09ef02)
![5d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/ca69c064-1048-480a-8e5d-3ea553011421)
![6d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/23e1557f-f764-4589-8a37-30d1677919bf)
### Adaptive Thresholding
![7d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/cc9b3845-06e0-4c6e-8d95-20f9bb93a315)
![8d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/72c3af41-e3d3-401e-9aca-2c4a2162108e)
### Optimum Global Thesholding using Otsu's Method
![9d](https://github.com/deepikasrinivasans/THRESHOLDING-/assets/119393935/dfb49ebf-c413-401d-b94d-3ab0f09e89fb)
## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
