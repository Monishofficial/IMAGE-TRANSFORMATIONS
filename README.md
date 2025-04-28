# EXP-4 IMAGE-TRANSFORMATIONS

## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import the necessary libraries and read the original image and save it as a image variable.

### Step2:
Translate the image using a function warpPerpective()

### Step3:
Scale the image by multiplying the rows and columns with a float value.

### Step4:
Shear the image in both the rows and columns.

### Step5:
Find the reflection of the image.

### Step6 :
Rotate the image using angle function.

## Program:
```
# Developed By: MONISH N
# Register Number: 212223240097

import cv2
import numpy as np

# Load the image (Corrected path - use raw string)
image = cv2.imread(r"C:\Users\admin\Downloads\imgage1.webp")  # Make sure the file exists
(h, w) = image.shape[:2]

# ----------------------- Translation -----------------------
# Move image 100 pixels right and 50 pixels down
tx, ty = 100, 50
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])
translated = cv2.warpAffine(image, translation_matrix, (w, h))

# ----------------------- Scaling -----------------------
# Resize by 1.5x horizontally and 0.75x vertically
scaled = cv2.resize(image, None, fx=1.5, fy=0.75, interpolation=cv2.INTER_LINEAR)

# ----------------------- Shearing -----------------------
# Shear image horizontally
shear_matrix = np.float32([[1, 0.5, 0], [0, 1, 0]])  # x-shear
sheared = cv2.warpAffine(image, shear_matrix, (int(w + 0.5 * h), h))

# ----------------------- Reflection (Flipping) -----------------------
# Flip horizontally (mirror image)
h_flip = cv2.flip(image, 1)
# Flip vertically
v_flip = cv2.flip(image, 0)

# ----------------------- Rotation -----------------------
# Rotate by 45 degrees around the center
angle = 45
scale = 1.0
center = (w // 2, h // 2)
rotation_matrix = cv2.getRotationMatrix2D(center, angle, scale)
rotated = cv2.warpAffine(image, rotation_matrix, (w, h))

# ----------------------- Cropping -----------------------
# Crop a region (top-left 200x200)
cropped = image[0:200, 0:200]

# ----------------------- Display Results -----------------------
cv2.imshow("Original", image)
cv2.imshow("Translated", translated)
cv2.imshow("Scaled", scaled)
cv2.imshow("Sheared", sheared)
cv2.imshow("Horizontally Flipped", h_flip)
cv2.imshow("Vertically Flipped", v_flip)
cv2.imshow("Rotated", rotated)
cv2.imshow("Cropped", cropped)

cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output:
### Original Image:
![Screenshot 2025-04-28 142043](https://github.com/user-attachments/assets/c5b83e31-5dfb-4108-b4da-dbeb973c147f)

### i)Image Translation
![Screenshot 2025-04-28 142113](https://github.com/user-attachments/assets/8ba509bb-0039-4124-afc1-8fe0e9544b65)

### ii) Image Scaling
![Screenshot 2025-04-28 142627](https://github.com/user-attachments/assets/0364d00a-033f-401e-a146-76850ff1ce32)

### iii)Image shearing
![Screenshot 2025-04-28 142705](https://github.com/user-attachments/assets/99eeaa48-2ec6-4c18-87aa-c49b3f827865)

#### i) Horizontally Flipped:
![Screenshot 2025-04-28 142857](https://github.com/user-attachments/assets/683527a0-8e28-49b1-b004-0674d712c808)

#### ii) Vertically Flipped:
![Screenshot 2025-04-28 142956](https://github.com/user-attachments/assets/affd6904-9fef-4c9b-ad15-7fcc7f35c4cc)

### v)Image Rotation
![Screenshot 2025-04-28 143017](https://github.com/user-attachments/assets/68fc7d56-5413-400e-964b-b2a3699467bf)

### vi)Image Cropping
![Screenshot 2025-04-28 143044](https://github.com/user-attachments/assets/f291a4c7-2864-4f9a-82c8-65a00d19afec)

## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.

