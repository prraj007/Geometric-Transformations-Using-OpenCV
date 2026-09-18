# Geometric Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to perform various geometric transformations on an image.

The program performs the following operations:

- Image Translation  
- Image Scaling (Resizing)  
- Image Shearing  
- Image Reflection (Flipping)  
- Image Rotation  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image in color mode.

### Step 3: Image Translation
- Create a translation matrix to shift the image  
- Move the image 50 pixels to the right and 80 pixels down  
- Apply transformation using `cv2.warpAffine()`  
- Display original and translated images  

### Step 4: Image Scaling
- Resize the image to 0.5× (downscale)  
- Resize the image to 2× (upscale)  
- Use `cv2.resize()`  
- Display original, downscaled, and upscaled images  

### Step 5: Image Shearing
- Create transformation matrices for:
  - Horizontal shearing  
  - Vertical shearing  
- Apply transformations using `cv2.warpAffine()`  
- Display original and sheared images  

### Step 6: Image Reflection
- Perform flipping using `cv2.flip()`:
  - Horizontal reflection  
  - Vertical reflection  
  - Both axes  
- Display all reflected images  

### Step 7: Image Rotation
- Create rotation matrices for:
  - 45° rotation  
  - 90° rotation  
- Use `cv2.getRotationMatrix2D()` and `cv2.warpAffine()`  
- Display original and rotated images  

---

##  Program

Register No:212225220116
Step 1:Import the required libraries
import cv2 import numpy as np import matplotlib.pyplot as plt

Step 2: Read the input image
img = cv2.imread(r"C:\Users\acer\Desktop\cars.jpg") rows, cols = img.shape[:2]

Helper function to display images separately
def show_image(title, image): plt.figure(figsize=(6,6)) plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) plt.title(title) plt.axis('off') plt.show()

Original
show_image("Original Image", img)

Step 3: Translation
M_translate = np.float32([[1, 0, 50], [0, 1, 80]]) translated = cv2.warpAffine(img, M_translate, (cols, rows)) show_image("Translated Image", translated)

Step 4: Scaling
downscaled = cv2.resize(img, None, fx=0.5, fy=0.5, interpolation=cv2.INTER_LINEAR) show_image("Downscaled Image (0.5x)", downscaled)

upscaled = cv2.resize(img, None, fx=2.0, fy=2.0, interpolation=cv2.INTER_LINEAR) show_image("Upscaled Image (2x)", upscaled)

Step 5: Shearing
M_shear_h = np.float32([[1, 0.5, 0], [0, 1, 0]]) sheared_h = cv2.warpAffine(img, M_shear_h, (int(cols*1.5), rows)) show_image("Horizontally Sheared Image", sheared_h)

M_shear_v = np.float32([[1, 0, 0], [0.5, 1, 0]]) sheared_v = cv2.warpAffine(img, M_shear_v, (cols, int(rows*1.5))) show_image("Vertically Sheared Image", sheared_v)

Step 6: Reflection
flip_h = cv2.flip(img, 1) show_image("Horizontally Flipped Image", flip_h)

flip_v = cv2.flip(img, 0) show_image("Vertically Flipped Image", flip_v)

flip_both = cv2.flip(img, -1) show_image("Flipped Both Axes", flip_both)

Step 7: Rotation
M_rotate_45 = cv2.getRotationMatrix2D((cols/2, rows/2), 45, 1) rotated_45 = cv2.warpAffine(img, M_rotate_45, (cols, rows)) show_image("Rotated Image (45°)", rotated_45)

M_rotate_90 = cv2.getRotationMatrix2D((cols/2, rows/2), 90, 1) rotated_90 = cv2.warpAffine(img, M_rotate_90, (cols, rows)) show_image("Rotated Image (90°)", rotated_90)

### Developed By:
**Name:**B.PRAVEEN RAJ

### Register No:
212225040315
---

##  Output

### Image Translation
- Original image is displayed
- <img width="602" height="368" alt="image" src="https://github.com/user-attachments/assets/fc9107c7-e1be-4fec-add0-c5d7ce2c7380" />

- Translated image (shifted right and down) is displayed
- <img width="636" height="372" alt="image" src="https://github.com/user-attachments/assets/8f2ea902-d304-4e47-9117-e3c880d6fec3" />


### Image Scaling
- Original image is displayed
- <img width="602" height="368" alt="image" src="https://github.com/user-attachments/assets/d5ffee71-7c42-4f6d-886c-cda5b02f78fd" />

- Downscaled image (0.5×) is displayed
- <img width="623" height="375" alt="image" src="https://github.com/user-attachments/assets/e41949e3-f093-48dd-837e-9a813cd454e7" />

- Upscaled image (2×) is displayed
- <img width="640" height="391" alt="image" src="https://github.com/user-attachments/assets/93bc1719-2970-4e57-a40d-bcbcf35e14c3" />


### Image Shearing
- Original image is displayed
- <img width="602" height="368" alt="image" src="https://github.com/user-attachments/assets/c8287520-c219-4007-a2e9-8d263f60984d" />

- Horizontally sheared image is displayed
- <img width="618" height="261" alt="image" src="https://github.com/user-attachments/assets/da50c2ad-b601-4b11-a02c-526ace271123" />

- Vertically sheared image is displayed
- <img width="622" height="529" alt="image" src="https://github.com/user-attachments/assets/84b91edf-66f9-407d-a7db-aca6833388fd" />


### Image Reflection
- Original image is displayed
- <img width="602" height="368" alt="image" src="https://github.com/user-attachments/assets/aaafa4db-320b-4a73-8a00-316ad80f2112" />

- Horizontally flipped image is displayed
- <img width="627" height="404" alt="image" src="https://github.com/user-attachments/assets/1e910ef8-888a-4ed8-8284-dc515d07f492" />

- Vertically flipped image is displayed
- <img width="594" height="394" alt="image" src="https://github.com/user-attachments/assets/3d57bfad-aeae-462d-9f81-48964e189b14" />

- Both-axis flipped image is displayed  
<img width="618" height="380" alt="image" src="https://github.com/user-attachments/assets/d4b59236-33c8-4d03-b184-4888ecf6ef0e" />

### Image Rotation
- Original image is displayed
- <img width="602" height="368" alt="image" src="https://github.com/user-attachments/assets/2322b2e4-e4a3-47c8-afb3-2d544b95c3d0" />

- 45° rotated image is displayed
- <img width="633" height="375" alt="image" src="https://github.com/user-attachments/assets/64c57734-abb8-47f9-8421-1591216bda59" />

- 90° rotated image is displayed
- <img width="615" height="369" alt="image" src="https://github.com/user-attachments/assets/65e91ec0-83a9-4963-b2b2-ba5d9c69e7d3" />


---

##  Result

Thus, various geometric transformations such as translation, scaling, shearing, reflection, and rotation are successfully performed using OpenCV. These transformations demonstrate how images can be spatially manipulated for different computer vision applications.
