# Image-Handling-and-Pixel-Transformations-Using-OpenCV 

## AIM:
Write a Python program using OpenCV that performs the following tasks:

1) Read and Display an Image.  
2) Adjust the brightness of an image.  
3) Modify the image contrast.  
4) Generate a third image using bitwise operations.

## Software Required:
- Anaconda - Python 3.7
- Jupyter Notebook (for interactive development and execution)

## Algorithm:
### Step 1:
Load an image from your local directory and display it.

### Step 2:
Create a matrix of ones (with data type float64) to adjust brightness.

### Step 3:
Create brighter and darker images by adding and subtracting the matrix from the original image.  
Display the original, brighter, and darker images.

### Step 4:
Modify the image contrast by creating two higher contrast images using scaling factors of 1.1 and 1.2 (without overflow fix).  
Display the original, lower contrast, and higher contrast images.

### Step 5:
Split the image (boy.jpg) into B, G, R components and display the channels

## Program Developed By:
- **Name:** LOGESHWARAN R
- **Register Number:** 212225040205

  ### Ex. No. 01

#### 1. Read the image ('loki1.jpeg') using OpenCV imread() as a grayscale image.
```python
import cv2
import matplotlib.pyplot as plt
```

#### 2. Read the saved image above as a color image using cv2.cvtColor():
```python
img = cv2.imread('loki1.jpeg', cv2.IMREAD_COLOR)
```

#### 3. Original Image:
```python
image = cv2.imread(r"C:\Users\syedf\Downloads\loki1.jpeg")
image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image)
plt.title("Original Image")
plt.axis('off')
plt.show()
```

#### 4. Convert Original Image with line from top left to right bottom
```python
path = r"C:\Users\syedf\Downloads\loki1.jpeg"
img = cv2.imread(path)
h, w = img.shape[:2]
cv2.line(img, (0, 0), (w-1, h-1), (255, 0, 0), 3)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.axis("off")
plt.show()
```

#### 5. Convert Original Image with Blue Circle
```python
img = cv2.imread(r"C:\Users\syedf\Downloads\loki1.jpeg")
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

cv2.circle(img_rgb, (w//2, h//2), min(w, h)//4, (0, 0, 255), 3)

plt.imshow(img_rgb)
plt.title("Image with Blue Circle")
plt.axis("off")
plt.show()
```

#### 6. Convert Original Image with RED Rectangle border:
```python
img = cv2.imread(r"C:\Users\syedf\Downloads\loki1.jpeg")
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

h, w = img_rgb.shape[:2]
cv2.rectangle(rectangle_img, (0, 0), (w-1, h-1), (0, 0, 255), 3)

plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis("off")
plt.show()
```

#### 7. Convert Original Image with Text
```python
img = cv2.imread(r"C:\Users\syedf\Downloads\loki1.jpeg")
height, width = img.shape[:2]
plt.imshow(img_rgb)
plt.title("Image with Text")
plt.axis("off")
plt.show()
```

#### 8. Convert Original Image into RGB
```python
img = cv2.imread(r"C:\Users\syedf\Downloads\loki1.jpeg")
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
height, width = img.shape[:2]
plt.imshow(img_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()
```

#### 9. Convert Original Image into HSV
```python
img_hsv = cv2.cvtColor(img_rgb, cv2.COLOR_RGB2HSV)
plt.figure(figsize=(8, 6))
plt.imshow(img_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()
```

#### 10. Convert Original Image into GrayScale
```python
gray_img = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
plt.figure(figsize=(8, 6))
plt.imshow(gray_img, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()
```

#### 11. Convert Original Image into YCrCb
```python
img_ycrcb = cv2.cvtColor(img, cv2.COLOR_BGR2YCrCb)
plt.figure(figsize=(8, 6))
plt.imshow(img_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()
```

#### 12. Convert HSV Image into RGB
```python
plt.figure(figsize=(8, 6))
plt.imshow(img_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()
```

#### 13.Convert Image with Center White Block
```python
x, y = (w - 600) // 2, (h - 600) // 2
cv2.rectangle(img, (x, y), (x + 599, y + 599), (255, 255, 255), -1)

plt.figure(figsize=(8, 6))
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title("Image with Center White Block")
plt.axis("off")
plt.show()

cv2.imwrite("output.png", img)
print("Image saved as output.png")
```

#### 14. Re-Sized Image (Half)
```python
img = cv2.imread(r"C:\Users\syedf\Downloads\loki1.jpeg")
resized = cv2.resize(img, (img.shape[1] // 2, img.shape[0] // 2))
plt.imshow(cv2.cvtColor(resized, cv2.COLOR_BGR2RGB))
plt.title("Image Resized (Half Size)")
plt.axis("off")
plt.show()
```

#### 15. Cropped Region of Interest (ROI)
```python
x, y = w // 2, h // 2
roi = img[y-50:y+50, x-50:x+50]
plt.figure(figsize=(3, 3))
plt.imshow(roi)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
```

#### 16. Image Flipped Horizontally
```python
flipped = cv2.flip(img, 1)
plt.imshow(cv2.cvtColor(flipped, cv2.COLOR_BGR2RGB))
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()
```

#### 17. Image Flipped Vertically
```python
flipped = cv2.flip(img, 0)
plt.imshow(cv2.cvtColor(flipped, cv2.COLOR_BGR2RGB))
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()
```

## Output:

## Original Image

<img width="335" height="517" alt="image" src="https://github.com/user-attachments/assets/8d9f5d0d-bfb6-4daf-bfa1-0d68f01edc72" />


## Convert Original Image with line from top left to right bottom

<img width="352" height="497" alt="image" src="https://github.com/user-attachments/assets/05286f95-6cf0-4fe1-bb65-031efcc96cff" />


## Convert Original Image with Blue Circle

<img width="347" height="516" alt="image" src="https://github.com/user-attachments/assets/b0e10cb4-9af6-41a2-bca1-49d72e9a0b19" />


## Convert Original Image with RED Rectangle border

<img width="331" height="521" alt="image" src="https://github.com/user-attachments/assets/c3e94cf9-acb0-4e5d-8579-896c67760622" />


## Convert Original Image with Text

<img width="302" height="515" alt="image" src="https://github.com/user-attachments/assets/4e8cc606-691a-4f8b-a4bd-8000dd9ffc05" />


## Convert Original Image into RGB

<img width="355" height="515" alt="image" src="https://github.com/user-attachments/assets/4ab00d7a-ae13-4205-930e-7849e042cf69" />


## Convert Original Image into HSV

<img width="431" height="636" alt="image" src="https://github.com/user-attachments/assets/9012e2b7-7225-4fbb-b225-64c51033447d" />


## Convert Original Image into GrayScale

<img width="362" height="647" alt="image" src="https://github.com/user-attachments/assets/24d638ee-3cf3-4bfc-a515-e507622ba55c" />


## Convert Original Image into YCrCb

<img width="386" height="647" alt="image" src="https://github.com/user-attachments/assets/fa0f6d38-640c-44fe-9f73-0272264210de" />

## Convert Image with Center White Block

<img width="467" height="632" alt="image" src="https://github.com/user-attachments/assets/7f3f7de1-cfc2-46d3-8d33-b3c50f058a7d" />


## Re-Sized Image (Half)

<img width="342" height="527" alt="image" src="https://github.com/user-attachments/assets/2927dab4-5702-4b72-9bc8-9c92282f1343" />

## Cropped Region of Interest (ROI)

<img width="390" height="355" alt="image" src="https://github.com/user-attachments/assets/1ecc8edf-7745-4f4c-9865-b3fbcb63617e" />

## Image Flipped Horizontally

<img width="335" height="527" alt="image" src="https://github.com/user-attachments/assets/f5b5fa5c-76e5-41b7-b291-c7a9c814fa0b" />

## Image Flipped Vertically

<img width="321" height="482" alt="image" src="https://github.com/user-attachments/assets/b148d8ca-1360-4233-8230-a23900d87180" />

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
