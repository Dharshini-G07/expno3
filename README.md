# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

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
## Name: Priyadharshini G
## Reg no : 212224230209
 

---

## Program

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('priya_grey.png', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
img = cv2.imread('priya_grey.png', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')

```


##  Output


<img width="253" height="436" alt="image" src="https://github.com/user-attachments/assets/7fefc5da-65ac-4d19-88fd-c5ff457cf26a" />

<img width="584" height="440" alt="image" src="https://github.com/user-attachments/assets/633eaef7-b178-4bba-897a-170c9405cf6e" />

<img width="580" height="450" alt="image" src="https://github.com/user-attachments/assets/d486ae2e-507d-4e6a-9bad-a5c33a37b5f7" />

<img width="249" height="437" alt="image" src="https://github.com/user-attachments/assets/c3aa9704-aa49-4fe9-bff9-2de0e1cfff40" />

<img width="579" height="434" alt="image" src="https://github.com/user-attachments/assets/673ef056-28b6-46e0-bf8d-d10beabb3946" />

<img width="272" height="440" alt="image" src="https://github.com/user-attachments/assets/13afc5da-c0b5-443f-823f-c7c966052b59" />

<img width="1061" height="425" alt="image" src="https://github.com/user-attachments/assets/1dedb0d9-9d1e-4635-bfa1-0d173fa5b2cf" />





---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
