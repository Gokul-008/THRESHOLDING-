## EX-08 THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.


### Software Required
1. Anaconda - Python 3.7
2. OpenCV
 
### Algorithm
#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.
### Program
```python
DEVELOPED BY: GOKUL.M
REGISTER NO: 212222230037
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("img1.jpEg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("img1.jpeg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```python
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

### Output
#### Original Image

![Screenshot 2024-04-10 110152](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/572c3dbe-478a-4880-adad-6a3e4de823bb)


#### Global Thresholding

![Screenshot 2024-04-10 110204](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/28503c15-3398-440e-a3aa-9a7dd4f1847b)

![Screenshot 2024-04-10 110215](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/cfef315e-9384-440d-814c-a73960510e18)

![Screenshot 2024-04-10 110225](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/af5c1105-0c2e-41d7-a4e1-3f54f1ff32f7)

![Screenshot 2024-04-10 110237](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/dcc2647c-9122-426d-af61-caede5f87b55)


![Screenshot 2024-04-10 110255](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/8afc9594-2bb3-4542-9071-ae15aae33118)



#### Adaptive Thresholding


![Screenshot 2024-04-10 110318](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/bfa75952-5ca2-44da-baf9-674c5a0470ae)
![Screenshot 2024-04-10 110333](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/9df2e7eb-9495-400b-a54e-9dfbd19aacee)


#### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-10 110305](https://github.com/Gokul-008/THRESHOLDING-/assets/121165996/d1b3b881-8a02-41d0-88dc-63b72a89b9f9)



### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.


