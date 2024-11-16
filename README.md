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
### Developed By:PRADEEP S
### Register Number: 212222100034


## Output:

### i) Read and display the image
```
   import cv2
   image=cv2.imread('Exp1.jpg',1)
   image=cv2.resize(image,(400,300))
   cv2.imshow('pradeep',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```
![a](https://github.com/user-attachments/assets/a12529fb-8b19-4730-b9dd-ad68a5127834)


### ii)Write the image

```
image=cv2.imread('Exp1.jpg',0)
cv2.imwrite('d.jpg',image)

```

![b](https://github.com/user-attachments/assets/d06fffb8-f937-4efd-9dc4-648732543e10)


### iii)Shape of the Image
```
image=cv2.imread('Exp1.jpg',1)
print(image.shape)
```

![c](https://github.com/user-attachments/assets/38b2f9a7-3f8b-4972-bea3-fd781d433734)


### iv)Access rows and columns
```
    import cv2
    import random
    image=cv2.imread('Exp1.jpg',1)
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
![d](https://github.com/user-attachments/assets/627cd946-3362-4512-81a5-3e9962918c34)


### v)Cut and paste portion of image
```
   image=cv2.imread('Exp1.jpg',1)
   image=cv2.resize(image,(400,400))
   tag =image[130:200,110:190]
   image[110:180,120:200] = tag
   cv2.imshow('partimage1',image)
   cv2.waitKey(0)
   cv2.destroyAllWindows()
```

![e](https://github.com/user-attachments/assets/17156c31-cd8c-4208-a2e7-89ba96314d6e)



### vi) BGR and RGB to HSV and GRAY
```
img = cv2.imread('Exp1.jpg',1)
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


![f](https://github.com/user-attachments/assets/551bd619-9690-499a-9627-0f9ad7a6976e)

### vii) HSV to RGB and BGR
```
img = cv2.imread('Exp1.jpg')
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
![g](https://github.com/user-attachments/assets/a14dd332-2836-4c3e-a392-6c3dbf2f34cb)


### viii) RGB and BGR to YCrCb
```
img = cv2.imread('Exp1.jpg')
img = cv2.resize(img,(300,200))
cv2.imshow('Original RGB Image',img)
YCrCb1 = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
cv2.imshow('RGB-2-YCrCb',YCrCb1)
YCrCb2 = cv2.cvtColor(img, cv2.COLOR_RGB2YCrCb)
cv2.imshow('BGR-2-YCrCb',YCrCb2)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

![i](https://github.com/user-attachments/assets/29587433-436d-40d0-8fde-3efaa48cd709)


### ix) Split and merge RGB Image
```
img = cv2.imread('Exp1.jpg',1)
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
![j](https://github.com/user-attachments/assets/6f39e0a8-c71e-494f-9fdc-967955d29cef)


### x) Split and merge HSV Image
```
img = cv2.imread("Exp1.jpg",1)
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

![k](https://github.com/user-attachments/assets/163aa5a8-7bb4-4c28-b6de-06390daabeae)


## Result:
Thus the images are read, displayed, and written ,and color conversion was performed between RGB, HSV and YCbCr color models successfully using the python program.







