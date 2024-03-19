# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step 1:
#### Import numpy module as np and pandas as pd.
<br>

### Step 2:
#### Assign the values to variables in the program.
<br>

### Step 3:
#### Get the values from the user appropriately.
<br>

### Step 4:
#### Continue the program by implementing the codes of required topics.
<br>

### Step 5:
#### Thus the program is executed in google colab.
<br>

## Program:

### Developed By : KANISHKAR M

### Register Number : 212222240044

#### Installing OpenCV , importing necessary libraries and displaying images  

```py
# Install OpenCV library
!pip install opencv-python-headless

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images 
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()


```
#### (i) Image Translation
```py
# Load an image from URL or file path
image_url = '1.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)
```

#### (ii) Image Scaling
```py

# Load an image from URL or file path
image_url = '2.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis


# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("Original Image:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

```




#### (iii) Image shearing
```py
# Load an image from URL or file path
image_url = '3.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)

```



#### (iv) Image Reflection

```py
# Load an image from URL or file path
image_url = '4.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)


```
##### (a) → Reflecting Horizontally

```py
# Display original and reflected images

show_image(image)
print("↑ Original Image")
show_image(reflected_image_horizontal)
print("↑ Reflected Horizontally")
```

##### (b) → Reflected Vertically

```py
show_image(image)
print("↑ Original Image")
show_image(reflected_image_vertical)
print("↑ Reflected Vertically")


```
##### (c) → Reflecting Horizontally & Vertically
```py

show_image(image)
print("↑ Original Image")
show_image(reflected_image_both)
print("↑ Reflected Both")

```

### (v) Image Rotation

```py
# Load an image from URL or file path
image_url = '5.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)


# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)


```


### (vi) Image Cropping

```py
# Load an image from URL or file path
image_url = '6.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)


```



## Output:

### (i) Image Translation
<br>
<br>

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/5ef8771e-5b26-4364-bb9f-76c9067cad73) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/a689e0f0-5012-4a26-bf60-75f2bad69c06)





<br>
<br>

### (ii) Image Scaling
<br>
<br>

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/b080c5b0-3bc8-4642-a7d8-b57dc62c871d) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/eebe805c-f0b5-411d-a5f5-de0aa7144ca0)





<br>
<br>


### (iii) Image shearing
<br>
<br>

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/2a4e4646-2b45-4c94-a807-39273f45141b) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/4e65674d-cd9c-4099-aec8-58305e88e46f)




<br>
<br>


### (iv) Image Reflection


#### Reflecting Horizontally

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/834c6f27-e4fa-481e-a38d-aa8769115eb5) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/8b859359-b271-4bff-98da-417b232613a4)




#### Reflecting Vertically

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/834c6f27-e4fa-481e-a38d-aa8769115eb5) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/bc10d84a-7cf7-43df-90a8-b20e84242345)




#### Reflecting Horizontally & Vertically


![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/834c6f27-e4fa-481e-a38d-aa8769115eb5) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/26a1324c-bc48-4206-a877-5d3fb49a7564)


<br>
<br>


### (v) Image Rotation
<br>
<br>

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/c11d65bc-f6cc-4f6e-b1ac-1bdb7e2d6dbf) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/2e4ce3df-b6cc-4c59-a6b9-bc1fb526f7bf)




<br>
<br>



### (vi) Image Cropping
<br>
<br>

![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/9cced89b-d2df-4f68-aff7-5dd9b997533d) ![image](https://github.com/KANISHKAR2607/IMAGE-TRANSFORMATIONS/assets/118886772/0a847c66-7cb6-43dd-b470-f1bb7a155763)



<br>
<br>




## Result: 

### Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
