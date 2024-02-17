# COLOR_CONVERSIONS_OF-IMAGE
## AIM
To write a python program using OpenCV to do the following image manipulations.

i) Read, display, and write an image.

ii) Access the rows and columns in an image.

iii) Cut and paste a small portion of the image.

iv)To perform the color conversion between RGB, BGR, HSV, and YCbCr color models.


## Software Required:
Anaconda - Python 3.7
## Algorithm:
### Step1:
Choose an image and save it as a filename.jpg ,
### Step2:
Use imread(filename, flags) to read the file.
### Step3:
Use imshow(window_name, image) to display the image.
### Step4:
Use imwrite(filename, image) to write the image.
### Step5:
End the program and close the output image windows.
### Step6:
Convert BGR and RGB to HSV and GRAY
### Step7:
Convert HSV to RGB and BGR
### Step8:
Convert RGB and BGR to YCrCb
### Step9:
Split and Merge RGB Image
### Step10:
Split and merge HSV Image

### Developed By:LATHISH KANNA.M
### Register Number:212222230073 

##### Program:
## Output:

### i) Read and display the image
```python
import cv2
img=cv2.imread('dpi .jpg',1)
cv2.imshow('colorimage',img)
cv2.waitKey(0)
```
#### output:
![Screenshot 2024-02-17 093747](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/3d3fbba0-3fd9-465b-9c32-c51a74fcdeaa)
<br>
<br>

### ii)Write the image
```python
import cv2
g_image=cv2.imread('dpi .jpg',0)
cv2.imwrite('dpi .jpg',g_image)
```
#### output:
![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/1d6d74a4-8356-4e97-a955-cda044ffa834)
<br>
<br>

### iii)Shape of the Image
```python
import cv2
image=cv2.imread('dpi .jpg',1)
print(image.shape)
```
#### output:
![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/4dd057b7-828c-4396-b150-3856f2d3e074)
<br>
<br>

### iv)Access rows and columns
```python
import random
import cv2
image=cv2.imread('dpi .jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### output:
![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/2424c367-f7cf-4dea-b219-d18ce5c6b982)
<br>
<br>

### v)Cut and paste portion of image
```python
   import cv2
   image=cv2.imread('dpi .jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[150:200,110:160]
   image[110:160,150:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
#### output:
![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/b3353fc9-8163-4e89-935e-8866334adf15)
<br>
<br>

### vi) BGR and RGB to HSV and GRAY
```python
import cv2
img = cv2.imread('dpi .jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)

hsv1 = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('BGR2HSV',hsv1)

hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)

gray1 = cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('BGR2GRAY',gray1)

gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### output:
![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/e1260274-49ad-49cd-9728-376fda9e2eef)
<br>
<br>

### vii) HSV to RGB and BGR
```python
import cv2
img = cv2.imread('dpi .jpg')
img = cv2.resize(img,(300,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### output:![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/e02d15a9-a9ad-4e75-8df2-aeb7eb6cf6d5)
<br>
<br>

### viii) RGB and BGR to YCrCb
```python
import cv2
img = cv2.imread('dpi .jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### output:![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/48e85f36-15db-42f7-8db4-0157b7466180)
<br>
<br>

### ix) Split and merge RGB Image
```python
import cv2
img = cv2.imread('dpi .jpg',1)
img = cv2.resize(img,(300,200))

R = img[:,:,2]
G = img[:,:,1]
B = img[:,:,0]

cv2.imshow('R-Channel',R)
cv2.imshow('G-Channel',G)
cv2.imshow('B-Channel',B)

merged = cv2.merge((B,G,R))
cv2.imshow('Merged RGB image',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### output:![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/c906e8a1-33b5-45e0-b12b-d54ac636ea5c)
<br>
<br>

### x) Split and merge HSV Image
```python
import cv2
img = cv2.imread("dpi .jpg",1)
img = cv2.resize(img,(300,200))
img=cv2.cvtColor(img,cv2.COLOR_RGB2HSV)

H,S,V=cv2.split(img)

cv2.imshow('Hue',H)
cv2.imshow('Saturation',S)
cv2.imshow('Value',V)

merged = cv2.merge((H,S,V))
cv2.imshow('Merged',merged)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### output:![image](https://github.com/lathishlathish/COLOR_CONVERSIONS_OF-IMAGE/assets/120359170/1cd8159a-ebda-488c-8262-bc92f714514b)
<br>
<br>

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







