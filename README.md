# Exp-5--Record-Implementation-of-Filters
# Developed By: BUSHPIKA C
# Register Number: 212225230038

## Aim

To implement filters for smoothing and sharpening images in the spatial domain.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Import the required libraries.

### Step 2
Read the image and convert it from BGR to RGB.

### Step 3
Apply the required smoothing and sharpening filters to the image separately.

### Step 4
Plot and display the original and filtered images using `matplotlib.pyplot`.

### Step 5
End the program.

## Program


## 1. Smoothing Filters

### i) Using Averaging Filter

```python
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("bushpika.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("on")
plt.show()
```

### ii) Using Weighted Averaging Filter

```python
kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("on")
plt.show())
```

### iii) Using Gaussian Filter

```python
gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("on")
plt.show()
```

### iv) Using Median Filter

```python
median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("on")
plt.show()
```

## 2. Sharpening Filters

### i) Using Laplacian Linear Kernel

```python
kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("on")
plt.show()
```

### ii) Using Laplacian Operator

```python
laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("on")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("on")
plt.show()
```

## Output

### 1. Smoothing Filters

#### i) Using Averaging Filter

<img width="986" height="713" alt="image" src="https://github.com/user-attachments/assets/e8290746-7e9c-40c8-86cb-04fa326fe396" />



#### ii) Using Weighted Averaging Filter

<img width="867" height="481" alt="image" src="https://github.com/user-attachments/assets/5fbf0c65-787d-4f2b-b194-6de61f21c50d" />


#### iii) Using Gaussian Filter


<img width="702" height="470" alt="image" src="https://github.com/user-attachments/assets/19f13b4d-be4d-4a4e-bf23-6f1a82bbf140" />



#### iv) Using Median Filter

<img width="915" height="747" alt="image" src="https://github.com/user-attachments/assets/12ceaf9c-67c5-4c44-bdf7-f420c0ba87c5" />



### 2. Sharpening Filters

#### i) Using Laplacian Kernel

<img width="718" height="470" alt="image" src="https://github.com/user-attachments/assets/924b1f27-e891-4cc6-8b68-fa70d34ec9b8" />

#### ii) Using Laplacian Operator

<img width="872" height="512" alt="image" src="https://github.com/user-attachments/assets/0ee9db72-2b2a-4d92-8374-d9c52b0ea083" />



## Result

Thus, filters were implemented for smoothing and sharpening images in the spatial domain using OpenCV and Python.
