# COLOR_CONVERSIONS_OF-IMAGE
## AIM:
To write a python program using OpenCV to do the following image manipulations.

## Software Required:
Anaconda - Python 3.7
## Algorithm:
```
1. Read and Display an Image:

Load an image from your local directory and display it.

2. Draw Shapes and Add Text:

Draw a line from the top-left to the bottom-right of the image.

Draw a circle at the center of the image.

o Draw a rectangle around a specific region of interest in the image.

Add the text "OpenCV Drawing" at the top-left corner of the image.

3. Image Color Conversion:

Convert the image from RGB to HSV and display it.

Convert the image from RGB to GRAY and display it.

O Convert the image from RGB to YCrCb and display it.

Convert the HSV image back to RGB and display it.

4. Access and Manipulate Image Pixels:

Access and print the value of the pixel at coordinates (100, 100). Modify the color of the pixel at (200, 200) to white.

5. Image Resizing:

Resize the original image to half its size and display it.

6. Image Cropping:

Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.

7. Image Flipping:

Flip the original image horizontally and display it.

Flip the original image vertically and display it.

8. Write and Save the Modified Image:

Save the final modified image to your local directory.
```

# Program:
```
Developed By: NARAMALA KUMARTEJA
Register Number: 212223230132
```


### 1.) Read and display the image

```Python
import cv2
image=cv2.imread('sun.jpg',1)
cv2.imshow('Image Window', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
``` 
 

### OUTPUT:

![image](https://github.com/user-attachments/assets/4c7cc8b3-8532-435c-ba3f-c9f59827765d)

 

### 2.) Draw Shapes and Add Text:
i)Draw a line from the top-left to the bottom-right of the image.

```Python
import cv2
img = cv2.imread("sun.JPG")
res = cv2.line(img, (0, 0), (599, 799), (200, 100, 205), 10)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()


```


### OUTPUT:

![image](https://github.com/user-attachments/assets/7816a976-6362-4419-9129-c8379a89be41)


 
### ii)Draw a circle at the center of the image.
```Python
import cv2

# Load the image
img = cv2.imread("sun.JPG")

# Get the dimensions of the image
height, width, _ = img.shape

# Calculate the center of the image
center_coordinates = (width // 2, height // 2)

# Draw a circle at the center of the image
res = cv2.circle(img, center_coordinates, 150, (255, 0, 0), 10)

# Display the image with the circle
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```


### OUTPUT:
![image](https://github.com/user-attachments/assets/b54f0529-b134-490e-a700-63b9efb15136)


      
### iii)Draw a rectangle around a specific region of interest in the image.
```Python
import cv2

img = cv2.imread("sun.JPG")
start=(0,0)
stop=(409,529)
color=(100,255,100)
thickness=10
res_img=cv2.rectangle(img,start,stop,color,thickness)
# Display the HSV image
cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
 

### OUTPUT:

![image](https://github.com/user-attachments/assets/313314bc-bb20-4dc2-8d97-167efa7b4aef)


      
### iv)Add the text "OpenCV Drawing" at the top-left corner of the image.

 ```Python
import cv2

# Load the image
img = cv2.imread("sun.JPG")

# Define the text to be added and its position
text = "OPENCV DRAWING"
position = (50, 50)  # Positioning the text at the top-left corner

# Set the font, scale, color, and thickness of the text
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
color = (255, 255, 255)  # White color
thickness = 2

# Add the text to the image
res = cv2.putText(img, text, position, font, font_scale, color, thickness, cv2.LINE_AA)

# Display the image with the text
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```

    
### OUTPUT:

![image](https://github.com/user-attachments/assets/7d07a5d8-17fb-4ca5-b3b6-32dd92a7d785)


### 3.)Image Color Conversion:
i)Convert the image from RGB to HSV and display it.
```Python
import cv2
img = cv2.imread('sun.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
hsv2 = cv2.cvtColor(img,cv2.COLOR_RGB2HSV)
cv2.imshow('RGB2HSV',hsv2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### OUTPUT:
![image](https://github.com/user-attachments/assets/c35d482d-d03e-4d0c-8ef9-714fdde8ea28)
#### ii.)Convert the image from RGB to GRAY and display it.
```Python
import cv2
img = cv2.imread('sun.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
gray2 = cv2.cvtColor(img,cv2.COLOR_RGB2GRAY)
cv2.imshow('RGB2GRAY',gray2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

### Output:
![image](https://github.com/user-attachments/assets/ca81baf3-c8bf-45f5-b101-864a1d2092e4)

#### iii.)Convert the image from RGB to YCrCb and display it.
```Python
import cv2
img = cv2.imread('sun.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![Screenshot 2024-09-10 114937](https://github.com/user-attachments/assets/0162a6cf-99e3-49bb-bf70-92d1c76e929a)

#### iv.)Convert the HSV image back to RGB and display it.
```Python
import cv2
img = cv2.imread('sun.jpg',1)
img = cv2.resize(img,(300,200))
cv2.imshow('Original Image',img)
BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/d7ab9071-a119-4488-991a-058e5c369c71)
## 4. Access and Manipulate Image Pixels:
```Python
import cv2

# Load and resize the image
img = cv2.imread('jesko.jpg', 1)
img = cv2.resize(img, (300, 200))

# Show the original image
cv2.imshow('Original Image', img)

# 1. Access and print the value of the pixel at coordinates (100, 100)
pixel_value = img[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")

# 2. Modify the color of the pixel at (199, 199) to white
img[199, 199] = [255, 255, 255]  # Setting the pixel value to white (BGR)

# Display the modified image
cv2.imshow('Modified Image', img)

# Wait for a key press and close the windows
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![image](https://github.com/user-attachments/assets/b6983bcd-a1d0-4494-a4d1-5c4b678af0b0)
## 5. Image Resizing:
```Python
width=600
height=800
half_width=300
half_height=400
resized_img = cv2.resize(image, (300, 400))
cv2.imshow('Original',image)
cv2.imshow('resized',resized_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![image](https://github.com/user-attachments/assets/8d9e2e92-8e2b-4636-927c-760f9f1cedd3)
## 6.Image Cropping:
```Python
import cv2

# Load the image
image1=cv2.imread('sun.jpg',1)

# Define the starting point and size of the ROI
x, y = 50, 50
width, height = 100, 100

# Crop the ROI
roi = image1[y:y + height, x:x + width]

# Display the cropped ROI
cv2.imshow('Cropped Image', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/cdd3fdac-85af-4769-8468-2d15103fb275)

## 7.Image Flipping:
i.)Flip the original image horizontally and display it.
```Python

import cv2
img = cv2.imread("sun.JPG")
img = cv2.resize(img,(300,200))
res=cv2.rotate(img,cv2.ROTATE_180)
cv2.imshow('Original',img)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
### Output:
![image](https://github.com/user-attachments/assets/3a081486-4833-4543-bcd2-8cb81b593124)


#### ii.)Flip the original image vertically and display it.

```Python
import cv2

img = cv2.imread("sun.JPG")
img = cv2.resize(img,(300,200))
res=cv2.rotate(img,cv2.ROTATE_90_CLOCKWISE)
# Display the HSV image
cv2.imshow('Original',img)
cv2.imshow('Image Window', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
### Output:
![image](https://github.com/user-attachments/assets/331ff3fc-e40a-4263-8cdf-34e39be32a68)

## 8. Write and Save the Modified Image:
```Python
import cv2
img = cv2.imread("sun.JPG")
img = cv2.resize(img,(300,200))
cv2.imwrite('sunny1.jpg',img)
```
### Output:
![image](https://github.com/user-attachments/assets/7f852761-6100-4118-aa7c-e2f6eaf8309d)

## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.


