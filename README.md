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

### Developed By: NARAMALA KUMARTEJA
### Register Number: 2122232132

<table>
  <tr>
    <td width=50%>


### i) Read and display the image
```Python
    import cv2
image=cv2.imread('teja.jpeg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Teja',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
  </td>
  <td>
    
#### OUTPUT:
![Screenshot 2024-08-14 152758](https://github.com/user-attachments/assets/25e77db9-4528-4626-b70c-e4f17331953f)
</td>
</tr>



<tr>
  <td width=50%>


### ii)Write the image
```Python
    import cv2
    image=cv2.imread('Teja.jpeg',0)
    cv2.imwrite('dw.jpeg',image)
```
  </td>
  <td>

#### OUTPUT:
![image](https://github.com/user-attachments/assets/32c1cc07-648c-4014-a61a-d89e14c6b05c)
</td>
</tr> 
<tr> 
  <td width=50%>

### iii)Shape of the Image
```Python
    import cv2
    image=cv2.imread('Teja.jpeg',1)
    print(image.shape)
```
  </td> 
  <td>

#### OUTPUT:
![image](https://github.com/user-attachments/assets/57b7296c-04d0-453b-a376-a36087a5de26)
  </td>
  </tr> 
  <tr>
    <td>
      
### iv)Access rows and columns
```Python
     import random
     import cv2
     image=cv2.imread('Teja.jpeg',1)
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
  </td>
  <td width="50%">

#### OUTPUT:
![Screenshot 2024-08-14 153156](https://github.com/user-attachments/assets/839fbb1d-7d9f-402a-9e0c-a05ccd60b265)


 </td>
 </tr>
 <tr>
  <td width=50%>

### v)Cut and paste portion of image
```Python
     import cv2
     image=cv2.imread('Teja.jpeg',1)
     image=cv2.resize(image,(400,400))
     tag =image[150:200,110:160]
     image[110:160,150:200] = tag
     cv2.imshow('partimage1',image)
     cv2.waitKey(0)
     cv2.destroyAllWindows()
```
  </td>
  <td>

#### OUTPUT:

![Screenshot 2024-08-14 153239](https://github.com/user-attachments/assets/b7a4f4d6-78a3-4d81-9f6d-ccdb88abb6e7)
 </td>
 </tr>
</table>

### vi) BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('Teja.jpeg',1)
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
#### OUTPUT:

![Screenshot 2024-08-14 153837](https://github.com/user-attachments/assets/35d77619-ce46-4d56-b42b-b9a983baebb3)

### vii) HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('teja.jpeg')
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
#### OUTPUT:

![Screenshot 2024-08-14 154019](https://github.com/user-attachments/assets/d705a755-6c9f-4f10-8d8c-7eacca5615d3)

### viii) RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('Teja.jpeg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
#### OUTPUT:

![image](https://github.com/user-attachments/assets/7b8732c0-2ba5-427e-bbf9-76a5de37fe08)


### ix) Split and merge RGB Image
```Python
import cv2
img = cv2.imread('Teja.jpeg',1)
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
#### OUTPUT:
![Screenshot 2024-08-14 154357](https://github.com/user-attachments/assets/748bc10f-916f-42b4-b1e2-b50f84ad5f98)



### x) Split and merge HSV Image
```Python
import cv2
img = cv2.imread("Teja.jpeg",1)
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
#### OUTPUT:
![Screenshot 2024-08-14 154557](https://github.com/user-attachments/assets/da2a7e26-8219-4f0d-ad45-c9711980aa3e)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.
