# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: MARINO SARISHA T
# Register Number: 212223240084

import cv2
import matplotlib.pyplot as plt
gray_image=cv2.imread('download.jpeg',cv2.IMREAD_GRAYSCALE)
color_img = cv2.imread("download.jpeg")
gray_hist = cv2.calcHist([gray_image], [0], None, [256], [0, 256])
hist_b = cv2.calcHist([color_img], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_img], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_img], [2], None, [256], [0, 256])
plt.figure(figsize=(12, 5))
```
![Screenshot 2025-04-22 153734](https://github.com/user-attachments/assets/205f76c1-a313-420d-852d-9d29f17e49f2)
```python
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
![Screenshot 2025-04-22 153742](https://github.com/user-attachments/assets/84271646-39d5-4d96-82f0-d1093baabadc)
```python
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-22 153750](https://github.com/user-attachments/assets/cce140c5-874d-4ba2-97ff-1f8ec48e94dc)
```python
plt.figure(figsize=(12, 5))
```
![Screenshot 2025-04-22 153756](https://github.com/user-attachments/assets/6c8a93ff-28e7-42f4-82ee-a688d5bdedd5)
```python
plt.plot(gray_hist, color='black')
plt.title("Grayscale Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")
```
![Screenshot 2025-04-22 153803](https://github.com/user-attachments/assets/6613c660-41b5-4ae4-98a3-18e5b2d65e49)
```python
plt.plot(hist_r, color='red')
plt.plot(hist_b, color='blue')
plt.plot(hist_g, color='green')
plt.title("Color Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")
plt.show()
```
![Screenshot 2025-04-22 153811](https://github.com/user-attachments/assets/6a0ef327-06b1-44e5-8f5f-29d194575314)
```python
equalized_grey_img = cv2.equalizeHist(gray_image)
plt.title("Equalized Hist of Gray Image")
plt.hist(equalized_grey_img.ravel(),bins=256,color='black',alpha=0.6)
plt.show()
```
![Screenshot 2025-04-22 153817](https://github.com/user-attachments/assets/026121db-317c-4e1c-9ce0-48e5e09e0641)

## Output:
### Input Grayscale Image and Color Image
![Screenshot 2025-04-22 153742](https://github.com/user-attachments/assets/39b89a3a-b613-40d8-a621-4548549c2f56)
![Screenshot 2025-04-22 153750](https://github.com/user-attachments/assets/04c49850-6be1-42c5-86a5-e57881d7ddaf)

### Histogram of Grayscale Image and any channel of Color Image

![Screenshot 2025-04-22 153803](https://github.com/user-attachments/assets/31668e6a-9c0f-459d-951e-2ee1a0cfdb7a)

![Screenshot 2025-04-22 153811](https://github.com/user-attachments/assets/622e2c68-0ab9-4806-b21b-89973c18b818)

### Histogram Equalization of Grayscale Image.
![Screenshot 2025-04-22 153817](https://github.com/user-attachments/assets/14ca924d-6e98-4d40-9ad3-65827ebc4117)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
