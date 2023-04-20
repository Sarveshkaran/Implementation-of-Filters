# Implementation-of-Filters
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

# Program:

```

 Developed By   : Monisha T
 Register Number: 212221240029

 1. Smoothing Filters

i) Using Averaging Filter


import cv2
import numpy as np
import matplotlib.pyplot as plt
image1 = cv2.imread("image.jpg")
image2 = cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel = np.ones((11,11),np.float32)/121
image3 = cv2.filter2D(image2,-1,kernel)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original")
plt.axis("Off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Filtered")
plt.axis('off')


ii) Using Weighted Averaging Filter


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("image.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
weighted_filter = cv2.filter2D(original_image,-1,kernel2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(weighted_filter)
plt.title("Filtered")
plt.axis("off")


iii) Using Gaussian Filter


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("image.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
gaussian_blur = cv2.GaussianBlur(src = original_image, ksize = (11,11), sigmaX=0, sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Filtered")
plt.axis("off")



iv) Using Median Filter


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("image.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
median = cv2.medianBlur(src=original_image,ksize = 11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Filtered")
plt.axis("off")



 2. Sharpening Filters
i) Using Laplacian Kernal


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("image.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernel3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
laplacian_kernel = cv2.filter2D(original_image,-1,kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_kernel)
plt.title("Filtered")
plt.axis("off"


ii) Using Laplacian Operator


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("image.jpg")
original_image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
laplacian_operator = cv2.Laplacian(original_image,cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(original_image)
plt.title("Original")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian_operator)
plt.title("Filtered")
plt.axis("off")

```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter

![output1](https://user-images.githubusercontent.com/93427240/167249305-965542b2-b5bf-4b7a-9282-2ad3146ca1ea.png)


ii) Using Weighted Averaging Filter

![output2](https://user-images.githubusercontent.com/93427240/167249339-da795754-d005-4e3d-8e5b-624759f26f00.png)


iii) Using Weighted Averaging Filter

![output3](https://user-images.githubusercontent.com/93427240/167249356-c9196617-ebfb-42c8-8e37-b93a73cb1362.png)


iv) Using Median Filter

![output4](https://user-images.githubusercontent.com/93427240/167249366-8629eb38-dd8d-4b15-8fef-c051c87dc907.png)


### 2. Sharpening Filters


i) Using Laplacian Kernal

![output5](https://user-images.githubusercontent.com/93427240/167249372-f59fc9cc-16ad-48b0-a9db-d1280705ddf6.png)


ii) Using Laplacian Operator

![output6 - Copy](https://user-images.githubusercontent.com/93427240/167249382-07402e26-4092-4a0a-9add-15cb21b98626.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
