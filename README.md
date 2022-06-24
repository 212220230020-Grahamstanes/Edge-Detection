### EX NO : 07
### DATE  : 17.05.2022
# <p align="center">Edge-Detection</p>
## Aim:

To perform edge detection using Sobel, Laplacian, and Canny edge detectors.

## Software Required:
Anaconda - Python 3.7

## ALGORITHM:
### Step 1:
Import the necessary modules.

### Step 2:
Perform edge detection on a image. 
- Sobel 
- Laplacian
- Canny

### Step 3:
Display the original images with edge detected images.

<br/>
<br/><br/>
<br/><br/>
<br/><br/>
<br/><br/>
<br/><br/>
<br/>

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
<br/>
<br/><br/>
<br/><br/>
<br/>

## Output:
### SOBEL EDGE DETECTOR
![1](https://user-images.githubusercontent.com/75235488/168804447-2d8d4a81-9192-4f3e-a9b0-e1667f736ece.png)
### LAPLACIAN EDGE DETECTOR
![2](https://user-images.githubusercontent.com/75235488/168804466-671b6cee-1dc0-4b6e-bb68-161159478af8.png)
### CANNY EDGE DETECTOR
![3](https://user-images.githubusercontent.com/75235488/168804486-a0d60d9f-2f46-45d6-9cd6-dc556bb54d6d.png)
## Result:
Thus the edges are detected using Sobel, Laplacian, and Canny edge detectors.
