# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image.
<br>

### Step6:
Display the results.
<br>

## Program
```
Developed by: HARISH G
Register number :212222243001
```
# Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```




# Read the Image and convert to grayscale
```python
image=cv2.imread("butterfly.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("butterfly.jpg",0)
```



# Use Global thresholding to segment the image
```python
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```



# Use Adaptive thresholding to segment the image
```python
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```



# Use Otsu's method to segment the image 
```python
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```



# Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
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

![Screenshot 2024-04-10 114617](https://github.com/Harish2404lll/THRESHOLDING-/assets/141472096/0e82d5f3-5486-4840-8cfb-4046529387d4)




### Global Thresholding
<br>![Screenshot 2024-04-10 132938](https://github.com/Harish2404lll/THRESHOLDING-/assets/141472096/e08cb0f3-4b11-42aa-af9e-f17e10337f4e)
![Screenshot 2024-04-10 133001](https://github.com/Harish2404lll/THRESHOLDING-/assets/141472096/0d2b901a-80f6-438a-995a-a8a9d3a91721)
![Screenshot 2024-04-10 133019](https://github.com/Harish2404lll/THRESHOLDING-/assets/141472096/de79c1ce-8b89-4741-812b-d13935e8aeae)




### Adaptive Thresholding

![Screenshot 2024-04-10 133056](https://github.com/Harish2404lll/THRESHOLDING-/assets/141472096/3230fd20-98b1-4401-9cd6-f9e654039c2e)




### Optimum Global Thesholding using Otsu's Method

![Screenshot 2024-04-10 133140](https://github.com/Harish2404lll/THRESHOLDING-/assets/141472096/fc49849e-0f88-4137-8f6f-855b05f05938)





## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
