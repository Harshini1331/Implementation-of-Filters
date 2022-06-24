# EX.NO : 06
# DATE :

# <p align="center">Implementation of Filters</p>

## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary modules.
</br> 

### Step2:
Average filter
```python
kernel=np.ones((11,11),np.float32)/121
image3=cv2.filter2D(image2,-1,kernel)
```
Weighted average filter
```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
```
Gaussian Blur
```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
```
Median filter
```python
median=cv2.medianBlur(image2,13)
```

### Step3:
For performing sharpening on a image. Laplacian Kernel
```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
```
Laplacian Operator
```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
```

### Step4
Display all the images with their respective filters.

## Program:
### Developed By   : Harshini M
### Register Number: 212220230022

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("image.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
```

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
ii) Using Weighted Averaging Filter
```Python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```
iii) Using Gaussian Filter
```Python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

iv) Using Median Filter
```Python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```
ii) Using Laplacian Operator
```Python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter
</br>
<img width="416" alt="image" src="https://user-images.githubusercontent.com/75235554/167906188-ab3f8924-e244-454b-bb46-44ca4a476cc5.png">
</br>

ii) Using Weighted Averaging Filter
</br>
<img width="430" alt="image" src="https://user-images.githubusercontent.com/75235554/167906250-51806c5d-9854-45cf-965e-9115b35f6c8c.png">
</br>

iii) Using Gaussian Filter
</br>
<img width="419" alt="image" src="https://user-images.githubusercontent.com/75235554/167906299-50d44644-474d-4e99-b360-92495f8cb965.png">
</br>

iv) Using Median Filter
</br>
<img width="415" alt="image" src="https://user-images.githubusercontent.com/75235554/167906348-d0ee3e5a-7209-46e0-b4b1-d5bbc1f86df1.png">
</br>

### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal
</br>
<img width="427" alt="image" src="https://user-images.githubusercontent.com/75235554/167906394-fbcfa989-7ee0-41fb-9cc8-700380ee6e55.png">
</br>

ii) Using Laplacian Operator
</br>
<img width="443" alt="image" src="https://user-images.githubusercontent.com/75235554/167906427-880360d7-3525-4a59-8d7a-2f407b4e16f8.png">
</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
