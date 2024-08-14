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

##### Program:
```
### Developed By: NARAMALA KUMARTEJA
### Register Number: 212223230132
```

### i) Read and display the image
```
import cv2
image=cv2.imread('teja.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Teja',image)
cv2.waitKey(0)
cv2.destroyAllWindows()


```
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/4ddb0956-d65c-43e6-97d4-ea74fe5ea4b9)

### ii)Write the image
```
import cv2
image=cv2.imread('Teja.jpg',0)
image=cv2.resize(image,(400,300))
cv2.imwrite('new1.png',image)
```

## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/b3695599-b014-4575-9084-7f8450e7230f)


### iii)Shape of the Image
```
import cv2
image=cv2.imread('Teja.jpg',1)
print(image.shape)
```

## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/f78af535-a673-4fd6-b018-78b89b850d44)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('Teja.jpg',1)
image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),random.randint(0,255),random.randint(0,255)] 
cv2.imshow('teja',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/9cf6e61e-500b-4666-8898-ac2cc0501ec3)

### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('teja.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('teja',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/4cc0e9f8-a0cd-43b7-8bb0-d5c209ca2a94)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('teja.jpg',1)
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
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/404cb81d-5a2e-459a-84b0-7a0d44b837e8)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/af83d613-53d3-42e7-bf52-41cb32edfcdc)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/ea9ab357-5b0b-48cf-a9bf-aecc5820317b)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/23f0002e-7794-416e-918e-07916a82a475)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/fa8cdbd0-c1ee-464c-824f-0844fb102dcf)

### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('Teja.jpg')
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
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/43e2cfed-c5e4-4573-87e4-8abfb93d8ef3)

![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/28ad39c0-2454-46b5-a861-538c40f0afbe)

![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/b9c272f1-376a-4ebe-9371-a3dd23f2cf1b)

### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('Teja.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/e8a695b7-4721-44c5-9a3e-0e733c443fcc)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/30d0aeb6-bf3f-4baf-b62a-5166e636e87c)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/364a39dc-d7ce-4605-be19-2b5889e355db)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('Teja.jpg',1)
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
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/fda68636-7339-4ad0-9fce-798693df8fa5)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/06a80016-8de9-482f-ae0c-d17891e8eb40)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/dac46315-edf4-4762-9bb8-762303ab2b33)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/6f14fac1-b2d5-4cc3-b4a7-e56c01e34c93)

### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("teja.jpg",1)
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
## OUTPUT:
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/cece4bb3-5e24-4c81-a03e-647a52b05832)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/69808926-0681-4ac2-ab0d-a3b8afa79eff)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/2088587c-91ce-47c4-9380-b83998c15942)
![image](https://github.com/saiganesh2006/COLOR_CONVERSIONS_OF-IMAGE/assets/145742342/ff03210c-f2ed-4274-800e-39cf014d99ff)



## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
