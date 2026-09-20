# NAME: kirupasagr S
# REG.No: 212224230126

# EX-04: Geometric-Transformations-Using-OpenCV
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
# Step 1: Load the image
~~~
image = cv2.imread('image.jpg')
~~~
# Display the original image
~~~
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")  
plt.axis('off')
~~~
# Step 2: Image Translation
~~~
tx, ty = 100, 50  # Translation factors (shift by 100 pixels horizontally and 50 vertically)
M_translation = np.float32([[1, 0, tx], [0, 1, ty]]) 
translated_image = cv2.warpAffine(image, M_translation, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(translated_image, cv2.COLOR_BGR2RGB)) e
plt.title("Translated Image")  
plt.axis('off')
~~~
# Step 3: Image Scaling
~~~
fx, fy = 5.0, 2.0  # Scaling factors (1.5x scaling for both width and height)
scaled_image = cv2.resize(image, None, fx=fx, fy=fy, interpolation=cv2.INTER_LINEAR)
plt.imshow(cv2.cvtColor(scaled_image, cv2.COLOR_BGR2RGB))e
plt.title("Scaled Image") 
plt.axis('off')
~~~
# Step 4: Image Shearing
~~~
shear_matrix = np.float32([[1, 0.5, 0], [0.5, 1, 0]])
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))
plt.imshow(cv2.cvtColor(sheared_image, cv2.COLOR_BGR2RGB))
plt.title("Sheared Image")
plt.axis('off')
~~~
# Step 5: Image Reflection
~~~
reflected_image = cv2.flip(image, 2)  # Flip the image horizontally (1 means horizontal flip)
# flip: 1 means horizontal flip, 0 would be vertical flip, -1 would flip both axes
plt.imshow(cv2.cvtColor(reflected_image, cv2.COLOR_BGR2RGB))
plt.title("Reflected Image")
plt.axis('off')
~~~
# Step 6: Image Rotation
~~~
(height, width) = image.shape[:2]  # Get the image height and width
angle = 45 
center = (width // 2, height // 2)  # Set the center of rotation to the image center
M_rotation = cv2.getRotationMatrix2D(center, angle, 1)
rotated_image = cv2.warpAffine(image, M_rotation, (width, height)) 
plt.imshow(cv2.cvtColor(rotated_image, cv2.COLOR_BGR2RGB))
plt.title("Rotated Image")
plt.axis('off')
~~~
# Step 7: Image Cropping
~~~
x, y, w, h = 100, 100, 200, 150 
cropped_image = image[y:y+h, x:x+w]
plt.imshow(cv2.cvtColor(cropped_image, cv2.COLOR_BGR2RGB))
plt.title("Cropped Image")
plt.axis('off')
~~~
---

###  Output
###orginal image
<img width="541" height="386" alt="image" src="https://github.com/user-attachments/assets/f69cabaf-2605-4cc3-ab76-6f607458ec1b" />

### Image Translation
- Original image is displayed  
- Translated image (shifted right and down) is displayed
- <img width="530" height="379" alt="image" src="https://github.com/user-attachments/assets/ee284535-0b87-4bf6-8dd9-3a9c6f706d6a" />
 

### Image Scaling
- Original image is displayed  
- Downscaled image (0.5×) is displayed  
- Upscaled image (2×) is displayed
-  <img width="539" height="173" alt="image" src="https://github.com/user-attachments/assets/afd12afa-6b78-4567-a697-fb1154b1681a" />


### Image Shearing
- Original image is displayed  
- Horizontally sheared image is displayed  
- Vertically sheared image is displayed
- <img width="547" height="383" alt="image" src="https://github.com/user-attachments/assets/1d6e47d3-ce73-4c4e-ab9d-5f45d595af42" />


### Image Reflection
- Original image is displayed  
- Horizontally flipped image is displayed  
- Vertically flipped image is displayed  
- Both-axis flipped image is displayed
- <img width="538" height="379" alt="image" src="https://github.com/user-attachments/assets/242a82ac-7333-436f-8083-59d42c2c9852" />


### Image Rotation
- Original image is displayed  
- 45° rotated image is displayed  
- 90° rotated image is displayed
- <img width="537" height="385" alt="image" src="https://github.com/user-attachments/assets/fcd94b36-523e-4a2a-b597-c2b1e263fd1b" />

### cropped image
<img width="532" height="422" alt="image" src="https://github.com/user-attachments/assets/0c8f9abe-45a4-485a-8789-5f37939bf081" />


---
