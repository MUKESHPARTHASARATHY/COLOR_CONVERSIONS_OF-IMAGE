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
### Developed By:MUKESH P
### Register Number: 212222240068


## Output:

### i, Read and display the image

```Python
import cv2
image=cv2.imread("image2.jpg")

cv2.imshow('nature',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
    
```
![image](https://github.com/user-attachments/assets/8d9bf02c-873f-4d37-b2e7-6b21cb7661d5)



### ii,Draw shapes and add text
#### Line
```Python

image=cv2.imread("image2.jpg")
diagonal = cv2.line(image,  (0, 0),(int(width * 2), int(height * 2))  
,(255, 0, 0),5)


cv2.imshow('Diagonal Line', diagonal)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/user-attachments/assets/365fd783-e064-414f-845b-5707950547dc)


#### Circle
```Python
import cv2
image = cv2.imread("image2.jpg")
image = cv2.resize(image, (500, 500))

res = cv2.circle(image,(250,250), 60, (0, 255, 0), 5)
cv2.imshow('vinush', res)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
![image](https://github.com/user-attachments/assets/1a1dc7a7-75b5-4660-9c17-6e46b2cf53c5)

#### Rectangle
```Python
import cv2
image = cv2.imread("image2.jpg")


img = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
img = cv2.imread("image2.jpg")
img = cv2.resize(img, (900, 612))
img.shape
start=(0,0)
stop=(900,612)
color=(100,255,100)
thickness=20

res_img=cv2.rectangle(img,start,stop,color,thickness)


cv2.imshow('Image Window', res_img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/f2889187-ade3-48f5-b281-4c4c3af3d8ff)
#### Add the text "OpenCV Drawing" at the top-left corner of the image.
```Python
image = cv2.imread("image2.jpg")
text = "OpenCV Drawing"
position = (10, 50)
font = cv2.FONT_HERSHEY_SIMPLEX
font_scale = 1
color = (255, 255, 255) 
thickness = 2
res = cv2.putText(image, text, position, font, font_scale, color, thickness, cv2.LINE_AA)
cv2.imshow('WINDOW', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/c607b0fd-6c92-48a4-8b6d-73d12d2bd821)


### iii) Image color conversion

#### BGR and RGB to HSV and GRAY
```Python
import cv2
img = cv2.imread('image2.jpg',1)
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
![image](https://github.com/user-attachments/assets/6e589b42-4a00-46b0-b17e-a1bee9ffa776)


#### HSV to RGB and BGR
```Python
import cv2
img = cv2.imread('image2.jpg')
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

![image](https://github.com/user-attachments/assets/55dac724-7bba-456f-91f8-3ebfebba88be)


#### RGB and BGR to YCrCb
```Python
import cv2
img = cv2.imread('image2.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/b6f28997-7097-4c7f-9926-4e3e7ad5b979)





#### Split and merge RGB Image
```Python
import cv2
img = cv2.imread('image2.jpg',1)
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
![image](https://github.com/user-attachments/assets/0d3467ce-f98a-4586-844e-d3c40098af06)


#### Split and merge HSV Image
```Python
import cv2
img = cv2.imread("image2.jpg",1)
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
![image](https://github.com/user-attachments/assets/a05fc6b7-ec55-4fa3-9e26-52d482c6a708)

### iv, Access and Manipulate Image Pixels
#### (1) Access and print the value of the pixel at coordinates (100, 100)
```Python
import cv2
image = cv2.imread("image2.jpg")
pixel_value = image[100, 100]
print(f"Pixel value at (100, 100): {pixel_value}")
```
![image](https://github.com/user-attachments/assets/36c347e7-c10d-4b4b-86e0-12e73f7c7a1f)


#### (2) Modify the color of the pixel at (200, 200) to white
```Python
import cv2
image = cv2.imread('image2.jpg',1)
image = cv2.resize(image,(400,300))
cv2.imshow('ORIGINAL IMAGE',image)
image[200, 200] = [255, 255, 255] 
cv2.imshow('MODIFIED IMAGE', image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/4254ed79-eabe-4d6f-b8ad-37e8acb60233)
### v, Image Resizing
```Python
cv2.imshow('ORIGINAL IMAGE',image)
resized_image = cv2.resize(image, (image.shape[1] // 2, image.shape[0] // 2))
cv2.imshow('RESIZED IMAGE', resized_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/1ac0d0f4-fc74-43c5-bdc7-951f858aaf6c)

### vi) Image Cropping
```Python
import cv2
image = cv2.imread('image2.jpg',1)
image = cv2.resize(image,(400,300))
x, y = 50, 50
width, height = 100, 100
roi = image[y:y + height, x:x + width]
cv2.imshow('CROPPED IMAGE', roi)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/e2fb4c46-5805-49f0-8017-56c08920a34e)

 ### vii) Image Flipping
 #### (1) Flip the original image horizontally and display it
```Python
import cv2
image = cv2.imread("image2.jpg")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_180)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
`
```
![image](https://github.com/user-attachments/assets/b22503e4-3712-4de1-892d-6af8e9ffabda)

#### (2) Flip the original image vertically and display it
```Python
import cv2
image = cv2.imread("image2.jpg")
image = cv2.resize(image,(300,200))
res=cv2.rotate(image,cv2.ROTATE_90_CLOCKWISE)
cv2.imshow('ORIGINAL IMAGE',image)
cv2.imshow('FLIPPED IMAGE', res)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![image](https://github.com/user-attachments/assets/afb4e35c-8679-40c0-8ce8-1ad0f753bc9c)

### viii)Write and Save the Modified Image
```Python
import cv2
img = cv2.imread("image2.jpg")
img = cv2.resize(img,(300,200))
cv2.imwrite('boat_pic.jpg',img)
```
![image](https://github.com/user-attachments/assets/81c5821e-7c98-4873-bf47-73ababe069ba)






## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







