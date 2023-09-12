# IMPLEMENTATION-OF-FILTERSS
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step2
Convert the saved BGR image to RGB using cvtColor().

### Step3
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4
Apply the filters using cv2.filter2D() for each respective filters.

### Step5
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
### Developed By   : Dharini PV
### Register Number: 212222240024

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("T&J.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/120
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(10,10))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("on")
plt.show()
```
ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("T&J.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/12
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (10,10))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Weighted Averaging Filter Image")
plt.axis("on")
```
iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("T&J.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (10,10))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Filter Image")
plt.axis("on")
```
iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("T&J.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (10,10))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Filter Image")
plt.axis("on")
```
### 2. Sharpening Filters
i) Using Laplacian Kernal
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("T&J.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (10,10))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Laplacian kernel Filtered Image")
plt.axis("on")
```
ii) Using Laplacian Operator
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("T&J.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (10,10))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title(" Laplacian operator Filtered Image")
plt.axis("on")
```

## OUTPUT:
### 1. Smoothing Filters
i) Using Averaging Filter
![Screenshot from 2023-09-12 09-48-34](https://github.com/DHARINIPV/IMPLEMENTATION-OF-FILTERSS/assets/119400845/bff6749a-5135-4a6a-bc21-01ca6b9f889c)


ii) Using Weighted Averaging Filter
![Screenshot from 2023-09-12 09-49-02](https://github.com/DHARINIPV/IMPLEMENTATION-OF-FILTERSS/assets/119400845/6a5f87d9-d518-46fa-aa3d-8e82d69fe718)


iii) Using Gaussian Filter
![Screenshot from 2023-09-12 09-49-37](https://github.com/DHARINIPV/IMPLEMENTATION-OF-FILTERSS/assets/119400845/4d6010a4-6d78-46d0-b742-34f08d0a0050)


iv) Using Median Filter
![Screenshot from 2023-09-12 09-50-08](https://github.com/DHARINIPV/IMPLEMENTATION-OF-FILTERSS/assets/119400845/03125584-0458-47a9-ba3e-8c563bb84ccd)

### 2. Sharpening Filters

i) Using Laplacian Kernal
![Screenshot from 2023-09-12 09-50-46](https://github.com/DHARINIPV/IMPLEMENTATION-OF-FILTERSS/assets/119400845/361ed892-e6a3-4427-8d0c-679e6eadd497)


ii) Using Laplacian Operator
![Screenshot from 2023-09-12 09-51-19](https://github.com/DHARINIPV/IMPLEMENTATION-OF-FILTERSS/assets/119400845/3886d8b5-7efc-4b76-8db8-b0bfe84ef72a)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
