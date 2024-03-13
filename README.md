\# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import numpy module as np and pandas as pd.

### Step2:
<br>
Assign the values to variables in the program.

### Step3:
<br>
Get the values from the user appropriately.

### Step4:
<br>
Continue the program by implementing the codes of required topics.

### Step5:
<br>
Thus the program is executed in google colab.

## Program:
```python
Developed By:A.Anbuselvam
Register Number:212222240009
```
i)Image Translation
```
import numpy as np
import cv2
import matplotlib.pyplot as plt

# Read the input image
input_image = cv2.imread("cat.jpg")

# Convert from BGR to RGB so we can plot using matplotlib
input_image = cv2.cvtColor(input_image, cv2.COLOR_BGR2RGB)

# Disable x & y axis
plt.axis('off')

# Show the image
plt.imshow(input_image)
plt.show()

# Get the image shape
rows, cols, dim = input_image.shape

# Transformation matrix for translation
M = np.float32([[1, 0, 100],
                [0, 1, 200],
                [0, 0, 1]])  # Fixed the missing '0' and added correct dimensions

# Apply a perspective transformation to the image
translated_image = cv2.warpPerspective(input_image, M, (cols, rows))

# Disable x & y axis
plt.axis('off')

# Show the resulting image
plt.imshow(translated_image)
plt.show()
```

ii) Image Scaling
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'nature.jpg'  # Replace with your image URL or file path
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


iii)Image shearing
```import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '3nat.jpg'  # Replace with your image URL or file path
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

iv)Image Reflection
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '4 nature.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

# Display original and reflected images
print("Original Image:")
show_image(image)
print("Reflected Horizontally:")
show_image(reflected_image_horizontal)
print("Reflected Vertically:")
show_image(reflected_image_vertical)
print("Reflected Both:")
show_image(reflected_image_both)
```

v)Image Rotation
```
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'nat5.jpg'  # Replace with your image URL or file path
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



vi)Image Cropping
```

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = '6nat.jpg'  # Replace with your image URL or file path
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
### i)Image Translation


![Screenshot 2024-03-13 110746](https://github.com/premalatha-sureshbabu/IMAGE-TRANSFORMATIONS/assets/120620842/548046b8-6518-42c6-9a64-189c5e04f929)

<br>
<br>

### ii) Image Scaling
<br>

![Screenshot 2024-03-13 110756](https://github.com/premalatha-sureshbabu/IMAGE-TRANSFORMATIONS/assets/120620842/29fa214d-3ccd-4d17-9b32-1867c176ea93)

<br>
<br>


### iii)Image shearing
<br>

![Screenshot 2024-03-13 110815](https://github.com/premalatha-sureshbabu/IMAGE-TRANSFORMATIONS/assets/120620842/c5d288e3-b44a-4b9b-96dd-68f56cc0bc98)

<br>
<br>


### iv)Image Reflection
<br>

![Screenshot 2024-03-13 110858](https://github.com/premalatha-sureshbabu/IMAGE-TRANSFORMATIONS/assets/120620842/41636717-c04c-4afe-a511-3c1f098f454c)

<br>
<br>



### v)Image Rotation
<br>

![Screenshot 2024-03-13 110937](https://github.com/premalatha-sureshbabu/IMAGE-TRANSFORMATIONS/assets/120620842/a66e4df3-1b1a-4dbe-85a1-2bd429f6369f)

<br>
<br>



### vi)Image Cropping
<br>

![Screenshot 2024-03-13 110947](https://github.com/premalatha-sureshbabu/IMAGE-TRANSFORMATIONS/assets/120620842/e5967a8e-fe45-4193-baa7-61240c7719be)

<br>
<br>




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
