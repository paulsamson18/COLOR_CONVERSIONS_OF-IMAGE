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
### Developed By:Subhikshaa M
### Register Number: 212222230151


## Output:

### i) Read and display the image
```
import cv2
import matplotlib.pyplot as plt

img=cv2.imread("duck.jpeg",1)
cv2.imshow("display window",img)
cv2.waitKey(0)
cv2.destroyAllWindows()
print(img.shape)
```

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/9b63115c-e20a-4c90-8367-d5b2f05f88e6)


### ii)Write the image

```
img1=cv2.imread("duck.jpeg",0)
cv2.imshow("display window",img1)
cv2.waitKey(0)
cv2.destroyAllWindows()
cv2.imwrite('greyscale.jpeg',img1)
```
![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/e476624c-4f25-4c8a-a4c8-5e0217852569)



### iii)Shape of the Image

```
import cv2
img1=cv2.imread("duck.jpeg",1)
print(img1.shape)
```
![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/b0a12699-0d5c-4641-a31f-5f54f32129c8)




### iv)Access rows and columns
```
import random
import cv2
image=cv2.imread('duck.jpeg',1)
#image=cv2.resize(image,(400,400))
for i in range (150,200):
    for j in range(image.shape[1]):
        image[i][j]=[random.randint(0,255),
                    random.randint(0,255),
                    random.randint(0,255)] 
cv2.imshow('part image',image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/3f7991d4-6e68-4950-ab74-40b337a5eb70)


### v)Cut and paste portion of image
```
import cv2

img2 = cv2.imread("duck.jpeg")

x = 0
y = 200
x1 = 160
y1 = 450
x2 = 0
y2 = 0

cropimg = img2[x:x1+x2, y:y1+y2]

cv2.imshow("Original Image", img2)
cv2.imshow("Cropped Image", cropimg)
cv2.waitKey(0)
cv2.destroyAllWindows()
```


![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/7472f89d-45db-4367-98f0-097ed4deb9f2)


![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/bb913ce5-5834-4061-842d-9dc1603b1c33)

### vi) BGR and RGB to HSV and GRAY
```
import cv2
img = cv2.imread('duck.jpeg',1)
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
![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/ba028e0e-6767-4446-902c-6fc3534ec91e)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/218629fe-feab-45d8-8e1f-9f575baa71e1)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/4fa1ae2a-7e1f-4b6f-accb-ae74bed09d52)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/11c00b88-fb20-41d8-a166-b977f0823380)




### vii) HSV to RGB and BGR
```
import cv2
img = cv2.imread('duck.jpeg')
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


![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/1bdb7a30-eaa6-4675-990f-8f2967c4a680)
![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/6f672cdb-c055-4ab7-aa03-0ea7475a000e)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/8c1f4fe3-d332-4353-8695-cf68c2701e7c)





### viii) RGB and BGR to YCrCb
```
import cv2
img = cv2.imread('duck.jpeg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)

YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)

YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)

cv2.waitKey(0)
cv2.destroyAllWindows()
```

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/9843fa37-7f02-40e3-8c09-16f458a3b578)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/10bfca00-3618-4e93-a680-40a8847eb494)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/313fad77-59cf-47a3-916a-6d6de9435730)


### ix) Split and merge RGB Image
```
import cv2
img = cv2.imread('duck.jpeg',1)
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

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/8829bd97-4563-4231-87d7-580b6d042b68)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/e28e691f-287e-43dc-9b8d-f0d4c09965b4)


![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/e12b4f53-8ac1-4a42-bdc8-a7d924dd38d0)


![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/5c51336c-e81c-437f-8a57-3b145563cd72)
### x) Split and merge HSV Image
```
import cv2
img = cv2.imread("duck.jpeg",1)
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

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/57d688ca-c128-4e67-8dd4-2de978a2e0a9)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/e5dee08a-47da-43d2-bf55-59439e470b48)


![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/3346e9e6-b1b8-4f77-9ac0-231bae64f161)

![image](https://github.com/Subhikshaa13/COLOR_CONVERSIONS_OF-IMAGE/assets/118787344/3690b21f-c501-4b6c-aaf8-53ca12fde404)




## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







