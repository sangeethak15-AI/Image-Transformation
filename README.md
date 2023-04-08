# Image-Transformation
## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the required libraries and read the original image.

### Step2:
Translate the image using M=np.float32([[1,0,20],[0,1,50],[0,0,1]]) translated_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step3:
scale the image using M=np.float32([[1.5,0,0],[0,2,0],[0,0,1]]) scaled_img=cv2.warpPerspective(input_img,M,(cols,rows))

### Step4:
Shear the image using M_x=np.float32([[1,0.2,0],[0,1,0],[0,0,1]])

### Step5:
Reflection of image can be achieved through the code M_x=np.float32([[1,0,0],[0,-1,rows],[0,0,1]]) .

### Step6:
Rotate the image using angle=np.radians(45).

### Step 7:
Crop the image using cropped_img=input_img[20:150,60:230]

### Step 8:
Display all the Transformed images and end the program.


## Program:
### Developed By:Sangeetha.K
#### Register Number:212221230085
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img=cv2.imread("ex5.jpg")
img=cv2.cvtColor(img,cv2.COLOR_BGR2RGB)
plt.axis('off')
plt.imshow(img)
plt.show()
```

i)Image Translation
```
rows,cols,dim=img.shape
m=np.float32([[1,0,50],[0,1,100],[0,0,1]])
translated_img=cv2.warpPerspective(img,m,(cols,rows))
plt.axis('off')
plt.imshow(translated_img)
plt.show()
```

ii) Image Scaling
```
rows,cols,dim=img.shape
m=np.float32([[1.5,0,0],[0,1.8,0],[0,0,1]])
scaled_img=cv2.warpPerspective(img,m,(cols*2,rows*2))
plt.imshow(scaled_img)
plt.show()
```
iii)Image shearing
```
x_axis=np.float32([[1,0.5,0],[0,1,0],[0,0,1]])
y_axis=np.float32([[1,0,0],[1,1,1],[0,0,1]])
sheared_ximg=cv2.warpPerspective(img,x_axis,(int(cols*1.5),int(rows*1.5)))
sheared_yimg=cv2.warpPerspective(img,y_axis,(int(cols*1.5),int(rows*1.5)))
plt.axis('off')
plt.imshow(sheared_ximg)
plt.show()
plt.axis('off')
plt.imshow(sheared_yimg)
plt.show()
```
iv)Image Reflection
```
x_axis=np.float32([[1,0,0],[0,-1,rows],[0,0,1]])
y_axis=np.float32([[-1,0,cols],[0,1,0],[0,0,1]])
reflected_ximg=cv2.warpPerspective(img,x_axis,(int(cols),int(rows)))
reflected_yimg=cv2.warpPerspective(img,y_axis,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(reflected_ximg)
plt.show()
plt.axis('off')
plt.imshow(reflected_yimg)
plt.show()
```
v)Image Rotation
```
angle=np.radians(10)
m=np.float32([[np.cos(angle), -(np.sin(angle)),0],
              [np.sin(angle),(np.cos(angle)),0],
              [0,0,1]])
rotated_img=cv2.warpPerspective(img,m,(int(cols),int(rows)))
plt.axis('off')
plt.imshow(rotated_img)
plt.show()
```
vi)Image Cropping
```
cropped_img=img[100:200,100:200]
plt.axis('off')
plt.imshow(cropped_img)
plt.show()
```

## Output:
### Original Image
![Screenshot 2023-04-08 102904](https://user-images.githubusercontent.com/93992063/230704153-5aac55a5-0f49-4b71-9e32-8467546f9521.png)


### i)Image Translation
![Screenshot 2023-04-08 103108](https://user-images.githubusercontent.com/93992063/230704156-019726c4-a0c4-4537-8bba-458e0a2374b2.png)


### ii) Image Scaling




### iii)Image shearing



### iv)Image Reflection




### v)Image Rotation




### vi)Image Cropping





## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
