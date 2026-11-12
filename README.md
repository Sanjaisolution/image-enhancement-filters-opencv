# EX.NO:05 - Image Smoothing and Sharpening Using OpenCV

## Aim

To write a Python program using OpenCV to apply different smoothing filters (Averaging, Weighted Averaging, Gaussian, Median) and sharpening filters (Laplacian Kernel and Laplacian Operator) for image enhancement, and display each result separately along with the original image for comparison.

---

## The program performs the following operations:

- Read and display an input image  
- Apply Averaging filter  
- Apply Weighted Averaging filter  
- Apply Gaussian filter  
- Apply Median filter  
- Apply Laplacian sharpening using kernel  
- Apply Laplacian operator  
- Display all outputs for comparison  

---

##  Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (cv2)  
- NumPy  
- Matplotlib  

---

##  Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the input image (e.g., `image.jpg`).

### Step 3:
Convert the image from BGR to RGB format for display.

### Step 4:
Apply Averaging Filter using `cv2.blur()`.

### Step 5:
Apply Weighted Averaging Filter using a custom kernel with `cv2.filter2D()`.

### Step 6:
Apply Gaussian Filter using `cv2.GaussianBlur()`.

### Step 7:
Apply Median Filter using `cv2.medianBlur()`.

### Step 8:
Apply Laplacian Sharpening using Kernel with `cv2.filter2D()`.

### Step 9:
Convert image to grayscale and apply Laplacian Operator using `cv2.Laplacian()`.

### Step 10:
Display all filtered images using a grid layout for comparison.

---

## Program & Output:

##  Developed By

- **Name:** SANJAI R
- **Register No:** 212223040180

```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("me.jpg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()
```
<img width="717" height="450" alt="21905512-ff0d-4f12-848f-f479cd55caea" src="https://github.com/user-attachments/assets/1f45b260-4682-4058-8c3d-bddfc8535268" />

```
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()
```

<img width="533" height="332" alt="201d522f-6e75-4acb-b581-bdcbdd23df93" src="https://github.com/user-attachments/assets/089298b8-a3fe-48a7-b478-69f3b69c55ed" />



```
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()
```

<img width="516" height="332" alt="0f63a5c7-56a0-4137-af49-c470459a7de7" src="https://github.com/user-attachments/assets/896723bd-04ad-4321-8daf-47fd6d6fde1c" />




```
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()
```

<img width="717" height="450" alt="469d8128-af11-4bdd-af92-323e2eafe76c" src="https://github.com/user-attachments/assets/c934d7ec-1d7f-4e11-9b30-3365ab6d8169" />




```
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()
```

<img width="516" height="332" alt="b298cb0a-58e6-4ca5-a19a-95d11e4c5619" src="https://github.com/user-attachments/assets/73571ba1-30bb-41ad-8239-df37c028537b" />


```
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```

<img width="516" height="332" alt="687e2799-6a35-46ec-a247-43f35dfbe72f" src="https://github.com/user-attachments/assets/9bfe9ba9-ba48-488c-9573-a81a08103dea" />

---


##  Result

Thus, smoothing filters and sharpening filters are successfully implemented using OpenCV.

The smoothing filters reduce noise and improve image quality, while sharpening filters enhance edges and details for better feature extraction.
