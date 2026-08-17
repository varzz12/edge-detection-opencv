# edge-detection-opencv

## Aim

To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

---

## Software Required

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

## ⚙️ Algorithm

### Step 1:
Import all the necessary modules for the program.

### Step 2:
Load an image using `cv2.imread()`.

### Step 3:
Convert the image to grayscale.

### Step 4:
Apply **Sobel operator** using OpenCV to detect edges.

### Step 5:
Apply **Prewitt operator** using custom kernels.

### Step 6:
Apply **Roberts operator** using custom kernels.

### Step 7:
Apply **Laplacian operator** using OpenCV.

### Step 8:
Apply **Canny edge detector** using OpenCV.

### Step 9:
Display all edge-detected images for comparison.

---

## Developed By

- **Name:** ____________________________  
- **Register No:** ______________________  

---

## Output

<img width="497" height="606" alt="image" src="https://github.com/user-attachments/assets/566c6648-a084-481a-90b0-3b480d2c6f3b" />

###  Sobel Edge Detector
```
- import cv2
import numpy as np
import matplotlib.pyplot as plt

image = cv2.imread('SAISHU.jpg') 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
<img width="461" height="602" alt="image" src="https://github.com/user-attachments/assets/20ad300a-98cc-4748-8d3b-93183fa3c5ce" />

###  Prewitt Edge Detector
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
<img width="480" height="600" alt="image" src="https://github.com/user-attachments/assets/2fe416ba-3bbc-4e89-a4dd-f746bab5f52f" />

###  Roberts Edge Detector
 <img width="513" height="590" alt="image" src="https://github.com/user-attachments/assets/dad2008c-1dce-47a1-bf3b-d9b7747fd277" />
 

###  Laplacian Edge Detector
```
Laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)
plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
```
<img width="495" height="600" alt="image" src="https://github.com/user-attachments/assets/296e2c59-1c05-48e4-a690-f1702268cdc1" />


###  Canny Edge Detector
```
image = cv2.imread("SAISHU.jpg")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(canny_edges, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off') 
```
<img width="446" height="601" alt="image" src="https://github.com/user-attachments/assets/1a0393a1-e098-42c1-8aec-56c4243553e9" />

---

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
