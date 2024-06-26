# EX NO-1
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
### Developed By:A.ANBUSELVAM
### Register Number: 212222240009


## Output:

### i) Read and display the image
```
import cv2
image=cv2.imread('anbu.png',1)
image=cv2.resize(image,(400,300))
cv2.imshow('anbu',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```





![image](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/48b54872-9843-4aa0-b7f6-f941771e9eb3)




### ii)Write the image
```
import cv2
image=cv2.imread('anbu.jpg',0)
cv2.imwrite('test.jpg',image)
```

![Screenshot 2024-05-07 110234](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/407a8241-0675-4e96-91a7-c6a586337fab)




### iii)Shape of the Image
```
import cv2
image=cv2.imread('anbu.jpg')
print(image.shape)
```

![Screenshot 2024-05-07 110424](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/d4dcf008-1ab6-42e4-87dd-0b38213b939c)



### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('anbu.pjg',1)
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

![Screenshot 2024-05-07 104314](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/970ad0fc-345d-4899-a982-27c601489ae2)



### v)Cut and paste portion of image
```
import cv2
image=cv2.imread('anbu.jpg',1)
image=cv2.resize(image,(400,400))
tag =image[150:200,110:160]
image[110:160,150:200] = tag
cv2.imshow('image1',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```
![Screenshot 2024-05-07 104404](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/18a578af-00ec-48a8-95b9-f5587c808880)



### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('anbu.jpg',1)
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

![Screenshot 2024-05-07 104909](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/86c63ec3-9b9e-4a56-8b2d-2e108b1c901f)



### vii) HSV to RGB and BGR
```
img = cv2.imread('anbu.jpg')
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

![Screenshot 2024-05-07 105251](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/cb23fea0-2541-46ae-8e83-c0340fcca7e0)



### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('anbu.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```


![Screenshot 2024-05-07 105344](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/65b85eed-905e-4d29-8657-ad9424b52194)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('anbu.jpg',1)
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
![Screenshot 2024-05-07 105656](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/21ef41d3-17d6-4acf-bec3-0954e8005c19)







### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("anbu.jpg",1)
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

![Screenshot 2024-05-07 105742](https://github.com/anbuselvamA/COLOR_CONVERSIONS_OF-IMAGE/assets/119559871/7364a71c-8046-4c8f-8568-7c02ea19faa7)



## Result:
    Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







