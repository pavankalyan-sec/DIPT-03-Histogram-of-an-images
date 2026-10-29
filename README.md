# DIPT-03-Histogram-of-an-images

# Name: Pavan Kalyan P
# Reg No: 212225240104

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the cv2.imread() function.

### Step 2
Display the grayscale and color images using the imshow() function.

### Step 3
Use the cv2.calcHist() function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the cv2.calcHist() function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

*Developed By:* SHRIVARSHAN P G

*Register Number:* 212225240146

python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('sv.jpeg', cv2.IMREAD_GRAYSCALE)

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

img = cv2.imread('sv.jpeg', cv2.IMREAD_COLOR)
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


## Output

### Input Grayscale Image

<img width="485" height="547" alt="image" src="https://github.com/user-attachments/assets/640efcee-4e3c-4c50-b5a9-3ee5c979c3b5" />

### Input Grayscale Image Range
<img width="797" height="537" alt="image" src="https://github.com/user-attachments/assets/90ef495e-a845-4ffa-a512-12548cd3e98d" />


### Input Grayscale Image Equalized Histogram
<img width="765" height="547" alt="image" src="https://github.com/user-attachments/assets/f16e3fd8-a967-49c9-b6eb-7c8ca8a61067" />



### Histogram of Grayscale Image and Color Image Channels

### Original Image

<img width="507" height="557" alt="image" src="https://github.com/user-attachments/assets/cb9a4076-9d5e-440a-b74a-c324eea5c13e" />


### Equalized Image

<img width="420" height="577" alt="image" src="https://github.com/user-attachments/assets/8e0b93c4-42ea-42cc-96b4-164ebf148ea4" />


### Equalized Histogram
<img width="752" height="530" alt="image" src="https://github.com/user-attachments/assets/32c4a4e1-5f0d-4e1b-bc6c-e625d25b62cd" />


### Final Output of Original Image and Equalized 
<img width="1086" height="375" alt="image" src="https://github.com/user-attachments/assets/2e0cad1d-778d-4c82-8104-a36880cd5038" />



### Final Output of Original Image and its Histogram Equalized
<img width="1087" height="307" alt="image" src="https://github.com/user-attachments/assets/63d0d46e-1eda-41d9-9277-4f8b60f42121" />



## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
