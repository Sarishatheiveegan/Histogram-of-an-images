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
![Screenshot 2025-04-25 220703](https://github.com/user-attachments/assets/cee4a833-868a-4e4a-a749-1aa3be603200)

```python
plt.imshow(gray_image, cmap='gray')
plt.title('Grayscale Image')
plt.axis('off')
```
![Screenshot 2025-04-25 220336](https://github.com/user-attachments/assets/0483241f-1c71-46a1-9e33-edeaa7ff42f8)

```python
plt.imshow(cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB))
plt.title('Color Image')
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-25 220343](https://github.com/user-attachments/assets/677e97c5-e88b-4b35-9edf-2b9301fd0232)

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
![Screenshot 2025-04-25 215953](https://github.com/user-attachments/assets/70007157-37b0-4710-b9ca-47f3f6280a9d)

```python
plt.plot(hist_r, color='red')
plt.plot(hist_b, color='blue')
plt.plot(hist_g, color='green')
plt.title("Color Image Histogram (Normalized)")
plt.xlabel("Pixel Intensity")
plt.ylabel("Normalized Pixel Count")
plt.show()
```
![Screenshot 2025-04-25 220005](https://github.com/user-attachments/assets/f31f935e-5d7f-4902-8864-c2a664fc13e1)

```python
equalized_grey_img = cv2.equalizeHist(gray_image)
plt.title("Equalized Hist of Gray Image")
plt.hist(equalized_grey_img.ravel(),bins=256,color='black',alpha=0.6)
plt.show()
```
![Screenshot 2025-04-22 153817](https://github.com/user-attachments/assets/026121db-317c-4e1c-9ce0-48e5e09e0641)

## Output:
### Input Grayscale Image and Color Image
![Screenshot 2025-04-25 220343](https://github.com/user-attachments/assets/2da6b95b-eea8-43c9-a5fb-f8bb9f96bf80)

![Screenshot 2025-04-25 220336](https://github.com/user-attachments/assets/159c37a2-d9b2-4eaa-977f-54a753c5471f)


### Histogram of Grayscale Image and any channel of Color Image
![Screenshot 2025-04-25 215953](https://github.com/user-attachments/assets/f3f01495-077c-4a45-95ad-b029c45f05ce)

![Screenshot 2025-04-25 220005](https://github.com/user-attachments/assets/ed86c23f-23bc-4ef1-a108-90746b574147)
### Histogram Equalization of Grayscale Image.
![Screenshot 2025-04-22 153817](https://github.com/user-attachments/assets/14ca924d-6e98-4d40-9ad3-65827ebc4117)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
