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
### Developed By:ANBU SELVAM A
### Register Number: 212222240009


## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('lion.jpg',1)
image=cv2.resize(image,(400,300))
cv2.imshow('Lion-Sathish',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
###output:


![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/4c052b30-3abe-4ea9-b767-f5c5cb4977f5)



### ii)Write the image
```
import cv2
image=cv2.imread('lion.jpg',0)
cv2.imwrite('test.jpg',image)
```
###Output:


![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/1f9a03a6-fbea-45fe-ae7c-a5eb9e16b427)


### iii)Shape of the Image
```
import cv2
image=cv2.imread('lion.jpg',1)
print(image.shape)
```
###output:


![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/e08ef7f9-8dab-4f27-b253-a20b53d876b4)

### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('lion.jpg',1)
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
###output:


![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/b3f99b78-e8f3-43fb-a1eb-093854689966)



### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('lion.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

###output:


![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/aca35e47-02d3-4494-b06a-84700cfcf407)


### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('lion.jpg',1)
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
###output:
![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/e8c84189-5241-41b7-9535-e019e2c30486)


### vii) HSV to RGB and BGR
```import cv2
img = cv2.imread('lion.jpg')
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
###output:
![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/dd55fb49-917d-4f7c-9abc-919fb51d2f6c)



### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('lion.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```
###output:
![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/fd64907d-cc45-4f50-b2d7-bb6e38f53db4)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('lion.jpg',1)
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
###output:
![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/ecaca5e6-6912-4a91-b850-36932843af0e)


### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("lion.jpg",1)
img = cv2.resize(img,(200,200))
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
###output:
![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/ed064070-8f65-4818-b8dd-7a662f5ceb5a)







## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







