Geometric Transformations Using OpenCV
Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

Image Translation
Image Scaling (Resizing)
Image Shearing
Image Reflection (Flipping)
Image Rotation
Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib
Algorithm
Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:

Read the input image in color mode.

Step 3: Image Translation
Create a translation matrix to shift the image
Move the image 100 pixels to the right and 50 pixels down
Apply transformation using cv2.warpAffine()
Display original and translated images
Step 4: Image Scaling
Resize the image using scaling factors
Use cv2.resize()
Display the scaled image
Step 5: Image Shearing
Create a shearing transformation matrix
Apply transformation using cv2.warpAffine()
Display the sheared image
Step 6: Image Reflection
Perform reflection using cv2.flip()
Display the reflected image
Step 7: Image Rotation
Rotate the image by 45°
Use cv2.getRotationMatrix2D() and cv2.warpAffine()
Display the rotated image
Step 8: Image Cropping
Define the cropping coordinates
Crop the required portion of the image
Display the cropped image
Program
Developed By:
Register No: 212224243005
Name: CJ ROHIT
Output
Image Translation
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Load the image
```PYTHON
image = cv2.imread('tamilnadumap.jpg')  # Load the image from file

# Display the original image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')
plt.show()

# Step 2: Image Translation
tx, ty = 100, 50  # Translation factors

M_translation = np.float32([
    [1, 0, tx],
    [0, 1, ty]
])

translated_image = cv2.warpAffine(
    image,
    M_translation,
    (image.shape[1], image.shape[0])
)

plt.imshow(
    cv2.cvtColor(
        translated_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Translated Image")
plt.axis('off')
plt.show()
Image Scaling
# Step 3: Image Scaling

fx, fy = 5.0, 2.0

scaled_image = cv2.resize(
    image,
    None,
    fx=fx,
    fy=fy,
    interpolation=cv2.INTER_LINEAR
)

plt.imshow(
    cv2.cvtColor(
        scaled_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Scaled Image")
plt.axis('off')
plt.show()
Image Shearing
# Step 4: Image Shearing

shear_matrix = np.float32([
    [1, 0.5, 0],
    [0.5, 1, 0]
])

sheared_image = cv2.warpAffine(
    image,
    shear_matrix,
    (image.shape[1], image.shape[0])
)

plt.imshow(
    cv2.cvtColor(
        sheared_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Sheared Image")
plt.axis('off')
plt.show()
Image Reflection
# Step 5: Image Reflection

reflected_image = cv2.flip(
    image,
    2
)

plt.imshow(
    cv2.cvtColor(
        reflected_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Reflected Image")
plt.axis('off')
plt.show()
Image Rotation
# Step 6: Image Rotation

(height, width) = image.shape[:2]

angle = 45

center = (
    width // 2,
    height // 2
)

M_rotation = cv2.getRotationMatrix2D(
    center,
    angle,
    1
)

rotated_image = cv2.warpAffine(
    image,
    M_rotation,
    (width, height)
)

plt.imshow(
    cv2.cvtColor(
        rotated_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Rotated Image")
plt.axis('off')
plt.show()
Image Cropping
# Step 7: Image Cropping

x, y, w, h = 100, 100, 200, 150

cropped_image = image[
    y:y+h,
    x:x+w
]

plt.imshow(
    cv2.cvtColor(
        cropped_image,
        cv2.COLOR_BGR2RGB
    )
)

plt.title("Cropped Image")
plt.axis('off')
plt.show()
```
OUTPUT:
<img width="497" height="1085" alt="Screenshot 2026-08-11 132110" src="https://github.com/user-attachments/assets/fa383cc5-f1c1-4bf9-9c79-207b34c49e9e" />
<img width="497" height="1085" alt="Screenshot 2026-08-11 132110" src="https://github.com/user-attachments/assets/f9b7bc01-0084-4f0a-8534-a032d76541f4" />
<img width="411" height="367" alt="Screenshot 2026-08-11 131904" src="https://github.com/user-attachments/assets/993a7f9a-11df-46c3-9c0f-e06ba441d0a8" />
<img width="513" height="988" alt="Screenshot 2026-08-11 131942" src="https://github.com/user-attachments/assets/de180f33-c58c-4cc8-a6ad-ee5bd8df6f57" />
<img width="512" height="1109" alt="Screenshot 2026-08-11 132007" src="https://github.com/user-attachments/assets/e907a19f-c398-47c1-b1f0-3f6e899df90e" />
<img width="497" height="1085" alt="Screenshot 2026-08-11 132110" src="https://github.com/user-attachments/assets/35739362-46ce-4a25-9377-9f932b2cc319" />


Result


Thus, various geometric transformations such as translation, scaling, shearing, reflection, rotation, and cropping are successfully performed using OpenCV on the image tamilnadumap.jpg.
