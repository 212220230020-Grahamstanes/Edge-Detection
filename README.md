# Edge-Detection
## Aim:

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary modules.
<br>


### Step2:
For performing edge detection on a image.

* Sobel
```
sobelx=cv2.Sobel(img,cv2.CV_64F,1,0,5)
sobely=cv2.Sobel(img,cv2.CV_64F,0,1,5)
sobelxy=cv2.Sobel(img,cv2.CV_64F,1,1,5)
```

* Laplacian
```
Laplacian=cv2.Laplacian(img,cv2.CV_64F)
```

* Canny
```
canny=cv2.Canny(img,120,150)
```
<br>

### Step3:
Display all the images with their respective edge detected images.
<br>
 
## Program:

``` Python
import cv2
import matplotlib.pyplot as plt
from cv2 import COLOR_BGR2GRAY
image=cv2.imread("image.jpg")
gray=cv2.cvtColor(image,COLOR_BGR2GRAY)

img = cv2.GaussianBlur(gray,(3,3),0)
sobelx = cv2.Sobel(img,cv2.CV_64F,1,0,ksize=5)
sobely = cv2.Sobel(img,cv2.CV_64F,0,1,ksize=5)
sobelxy =cv2.Sobel(img,cv2.CV_64F,1,1,ksize=5)

plt.figure(1)
plt.subplot(2,2,1)
plt.imshow(img,cmap = 'gray')
plt.title('Original'), plt.xticks([]), plt.yticks([])

plt.subplot(2,2,2)
plt.imshow(sobelx)
plt.title('sobelx')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,3)
plt.imshow(sobely)
plt.title('sobely')
plt.xticks([]), plt.yticks([])

plt.subplot(2,2,4)
plt.imshow(sobelxy)
plt.title('sobelxy')
plt.xticks([]), plt.yticks([])
plt.show()

laplacian = cv2.Laplacian(img,cv2.CV_64F)
plt.imshow(laplacian)
plt.title('laplacian')
plt.axis("off")
plt.show()

canny_edges = cv2.Canny(img, 120, 150)
plt.imshow(canny_edges)
plt.title('canny_edges')
plt.axis("off")
plt.show()
```
## Output:
### SOBEL EDGE DETECTOR

![image](https://user-images.githubusercontent.com/75235150/169490690-4d3e2d6a-dcda-4c45-99c6-6ae8f3751ab1.png)



### LAPLACIAN EDGE DETECTOR

![image](https://user-images.githubusercontent.com/75235150/169490736-9cbadbc1-5d6d-4778-a454-36e3ecf8f2a1.png)



### CANNY EDGE DETECTOR

![image](https://user-images.githubusercontent.com/75235150/169490784-361b9887-5c56-46b0-8a9e-1619b5310439.png)



## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
