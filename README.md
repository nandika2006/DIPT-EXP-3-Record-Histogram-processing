# EX. NO: 03
# Histogram Equalization Using OpenCV (Grayscale & Color Images)

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program

### Developed By:
**Name:** NANDIKA S

### Register No:
212224230175
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('pa.jpeg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()

# Read the image in grayscale format
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()

# Perform histogram equalization
img_eq = cv2.equalizeHist(img)

# Display [1] the Original Image (Gray Image) and its Histogram, and [2] the Enhanced Image and its Histogram using a 2×2 layout in Matplotlib.

plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()

# Read the colorgiven parrot.jpg image.

img = cv2.imread('pa.jepg', cv2.IMREAD_COLOR)

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

# Convert to HSV.
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])

# Perform histogram equalization

img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

# Convert back to BGR format

plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')

plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```

##  Output:

### Grayscale Histogram Equalization

1. Original grayscale image is displayed
<img width="730" height="508" alt="image" src="https://github.com/user-attachments/assets/bc2bb441-f556-4f95-b2a1-e9b06369e839" />

2. Histogram of original grayscale image is plotted
<img width="717" height="530" alt="image" src="https://github.com/user-attachments/assets/116d6fdd-ff1c-4a73-b5f4-7e3bffe60a3d" />

3. Enhanced image after histogram equalization is displayed
<img width="730" height="516" alt="image" src="https://github.com/user-attachments/assets/63cd77e6-5958-48b4-8e2a-5a5c3d40951a" />
 
4. Histogram of enhanced grayscale image shows improved contrast
<img width="733" height="520" alt="image" src="https://github.com/user-attachments/assets/3c6fa678-c0e6-4732-96fa-c284d6d77096" />


### Color Image Histogram Equalization

1. Original color image is displayed
<img width="750" height="501" alt="image" src="https://github.com/user-attachments/assets/7903e0f8-1c05-4687-a510-517e0bc33e18" />

2. Histogram of B, G, R channels is plotted
<img width="730" height="521" alt="image" src="https://github.com/user-attachments/assets/d2a189cf-dc24-4f3d-a1f5-b5e4b6de3933" />
 
3. Enhanced image after HSV-based equalization is displayed
<img width="728" height="237" alt="image" src="https://github.com/user-attachments/assets/e9726e5b-1828-40bc-b499-85e276d1d44a" />

4. Histogram of enhanced image shows better intensity distribution  
<img width="737" height="233" alt="image" src="https://github.com/user-attachments/assets/cfbb9626-2d34-431e-a28a-bc3e0fd83c3c" />

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
