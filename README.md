# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1: 
Import the necessary libraries and read two images, Color
image and Gray Scale image.

### Step 2:
Calculate the Histogram of Gray scale image and any one channel of the color image.

### Step 3:
Display the histograms.

### Step 4:
Equalize the color image.

### Step 5:
Display the equalized grayscale image.

## Program:
```python
# Developed By: Prasannalakshmi G
# Register Number: 212222240075


import cv2
import matplotlib.pyplot as plt
Gray_image=cv2.imread('grayscale.png')
plt.imshow(Gray_image)
plt.show()
Color_image=cv2.imread('colorimage.png')
plt.imshow(Color_image)
plt.show()

# Write your code to find the histogram of gray scale image and color image channels :

hist=cv2.calcHist([Gray_image],[0],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("gray_scale value")
plt.ylabel("pixel count")
plt.stem(hist)
plt.show()

# Display the histogram of gray scale image and any one channel histogram from color image

hist1=cv2.calcHist([Color_image],[1],None,[256],[0,256])
plt.figure()
plt.title("Histogram")
plt.xlabel("color_scale value")
plt.ylabel("pixel count")
plt.stem(hist1)
plt.show()

# Write the code to perform histogram equalization of the image. 

equ=cv2.equalizeHist(cv2.imread('colorimage.png',0))
equ=cv2.cvtColor(equ,cv2.COLOR_BGR2RGB)
plt.title("Equalised Image")
plt.axis("off")
plt.imshow(equ)
plt.show()

```
## Output:

## Input Grayscale Image and Color Image :
![OUTPUT](./sun1.png)

![OUTPUT](./sun2.png)

## Histogram of Grayscale Image and any channel of Color Image :

![OUTPUT](./sun3.png)

![OUTPUT](./sun4.png)



## Histogram Equalization of Grayscale Image :

![OUTPUT](./sun5.png)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
