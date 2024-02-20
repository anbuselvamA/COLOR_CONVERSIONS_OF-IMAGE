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
### Developed By: RAKESH V
### Register Number: 212222110036


## Output:

### i) Read and display the imageimport cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(300,300))
    cv2.imshow('BEULAH',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()

## 
OUTPUT:
![DIP IMG 1](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/066aaad7-9c8b-4e8e-992c-36a3c4dceb87)



### ii)Write the image

    import cv2
    image=cv2.imread('dog.jpg',0)
    cv2.imwrite('demos.jpg',image)

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/de980f83-8f4e-44da-a7c6-6e6a6e103dbf)



### iii)Shape of the Image

    import cv2
    image=cv2.imread('dop.jpg',1)
    print(image.shape)

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/d6991895-2a44-407f-9f31-e71af620da2e)



### iv)Access rows and columns
    import random
    import cv2
    image=cv2.imread('dog.jpg',1)
    image=cv2.resize(image,(500,500))
    for i in range (250,500):
      for j in range(image.shape[1]):
          image[i][j]=[random.randint(0,255),
                       random.randint(0,255),
                       random.randint(0,255)] 
    cv2.imshow('part image',image)
    cv2.waitKey(0)
    cv2.destroyAllWindows()

## OUTPUT
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/27dce278-6047-46ce-b3d1-5b47ba431c9a)


### v)Cut and paste portion of image
  import cv2
  image=cv2.imread('dog.jpg',1)
  image=cv2.resize(image,(300,300))
  tag =image[150:200,110:160]
  image[110:160,150:200] = tag
  cv2.imshow('image1',image)
  cv2.waitKey(0)
  cv2.destroyAllWindows()

## OUTPUT
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/fc742d94-c8b5-4b0f-a719-226f0db49515)

### vi) BGR and RGB to HSV and GRAY
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))
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

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/aa630103-018f-462f-a9f0-85202730fa13)


### vii) HSV to RGB and BGR
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))

img = cv2.cvtColor(img,cv2.COLOR_BGR2HSV)
cv2.imshow('Original HSV Image',img)

RGB = cv2.cvtColor(img,cv2.COLOR_HSV2RGB)
cv2.imshow('2HSV2BGR',RGB)

BGR = cv2.cvtColor(img,cv2.COLOR_HSV2BGR)
cv2.imshow('HSV2RGB',BGR)

cv2.waitKey(0)
cv2.destroyAllWindows()

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/4e932e65-adb8-47a2-8087-8825e277929a)



### viii) RGB and BGR to YCrCb
import cv2
img = cv2.imread('dog.jpg')
img = cv2.resize(img,(200,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/f871033d-a478-4778-b19f-8438d5c97fb1)



### ix) Split and merge RGB Image
import cv2
img = cv2.imread('dog.jpg',1)
img = cv2.resize(img,(200,200))

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

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/f8c1bfa8-bb25-41c8-be27-5fefc2e3684b)


### x) Split and merge HSV Image
import cv2
img = cv2.imread("dog.jpg",1)
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

## OUTPUT:
![image](https://github.com/rakeshcoder2004/COLOR_CONVERSIONS_OF-IMAGE/assets/121490890/1b0ef0d0-0b8d-4f71-9908-36b220636364)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







