# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
Import all the necessary modules 
### Step 2:
Choose an image and save it as filename.jpg
### Step 3:
Use imread to read the image
### Step 4:
Use cv2.warpPerspective(image,M,(cols,rows)) to translation the image
### Step 5:
Use cv2.warpPerspective(image,M,(cols2,rows2)) to scale the image
### Step 6:
Use cv2.warpPerspective(image,M,(int(cols1.5),int(rows1.5))) for x and y axis to shear the image
### Step 7:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) for x and y axis to reflect the image
### Step 8:
Use cv2.warpPerspective(image,M,(int(cols),int(rows))) to rotate the image
### Step 9:
Crop the image to remove unwanted areas from an image
### Step 10:
Use cv2.imshow to show the image
### Step 11: End the program


## Program:
```python
Developed By: shruthi D.N
Register Number: 212223240155

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('flower.jpeg')
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
```
i)Image Translation
```
tx, ty = 100, 50
M_translation = np.float32([[1, 0, tx], [0, 1, ty]])
# [1, 0, tx] - Horizontal shift by tx
# [0, 1, ty] - Vertical shift by ty
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB))
plt.title("Translated Image")
plt.axis('off')
```

ii) Image Scaling
```
fx, fy = 5.0, 2.0 # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB)) # Display the scaled image
plt.title("Scaled Image") # Set title
plt.axis('off')
```

iii)Image shearing
```
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]]) # Shearing matrix
# The matrix shears the image by a factor of 0.5 in both x and y directions
# [1, 0.5, 0] - Shear along the x-axis (horizontal)
# [0.5, 1, 0] - Shear along the y-axis (vertical)
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB)) # Display the sheared image
plt.title("Sheared Image") # Set title
plt.axis('off')
```


iv)Image Reflection
```
reflected_image = cv2.flip(image, 2)
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB)) # Display the reflected image
plt.title("Reflected Image") # Set title
plt.axis('off')
```



v)Image Rotation

```
(height, width) = image.shape[:2] # Get the image height and width
angle = 45 # Rotation angle in degrees (rotate by 45 degrees)
center = (width // 2, height // 2) # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1) # Get the rotation matrix
# getRotationMatrix2D: Takes the center of rotation, angle, and scale factor (1 means no scaling
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) # Apply rotation
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB)) # Display the rotated image
plt.title("Rotated Image") # Set title
plt.axis('off')
```


vi)Image Cropping

```
x, y, w, h = 100, 100, 200, 150 # Define the top-left corner (x, y) and the width (w) and heigh
# Cropping the image from coordinates (x, y) to (x+w, y+h)
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB)) # Display the cropped image
plt.title("Cropped Image") # Set title
plt.axis('off')


```

## Output:
### i)Image Translation
<img width="774" height="492" alt="image" src="https://github.com/user-attachments/assets/54838778-5cd9-4cd5-8a6e-44d42164b7a6" />



### ii) Image Scaling
<img width="794" height="232" alt="image" src="https://github.com/user-attachments/assets/0b53c542-f373-4197-a58e-cd201a092b83" />



### iii)Image shearing
<img width="769" height="500" alt="image" src="https://github.com/user-attachments/assets/5055ada4-dee9-4e60-90b5-683f0b7cd9dc" />



### iv)Image Reflection
<img width="831" height="439" alt="image" src="https://github.com/user-attachments/assets/ad0f2889-eb09-40e7-912c-ddc3ab1e9f27" />



### v)Image Rotation
<img width="726" height="504" alt="image" src="https://github.com/user-attachments/assets/c026a1f4-9ced-4f41-93c7-016ed9ddfb41" />



### vi)Image Cropping
<img width="1014" height="419" alt="image" src="https://github.com/user-attachments/assets/75dc54aa-dc22-4059-91c8-60883bfe2ac7" />



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
