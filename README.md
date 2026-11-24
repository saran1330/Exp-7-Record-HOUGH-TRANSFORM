# Detect-the-lines-using-Hough-Transform

##  Developed By: SARAN RAJ M

## Register: No: 212225240138

##  Aim

To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

---

## Learning Objective

* Understand each stage of image processing
* Learn how to build a complete computer vision pipeline
* Practice writing code in guided sections

---

##  Software Used

* Anaconda – Python 3.7
* Jupyter Notebook / VS Code
* OpenCV (cv2)
* NumPy
* Matplotlib

---

##  Algorithm & Explanation

---

###  Step 1: Import Libraries

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```

---

###  Step 2: Read the Image

```
image = cv2.imread('loki1.jpeg') 
```

---

###  Step 3: Convert to Grayscale

```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```

---

###  Step 5: Display Images

```

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
```

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

---

### Step 6: Edge Detection (Canny)

```
edges = cv2.Canny(gray_image, 50, 150)
```

```
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

---


###  Step 7: Hough Transform

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)

for line in lines:
    x1, y1, x2, y2 = line.flatten()
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```

---

### Step 8: Display the result of Hough Transform (Image with lines):
```
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Result of Hough Transform")
plt.axis('off')
```

---

## Output:

## Original image:


<img width="447" height="307" alt="Screenshot 2026-11-24 085333" src="https://github.com/user-attachments/assets/4b4bd6c5-9ea0-444c-99a2-d13f2eb87943" />


## Grayscale image:

<img width="452" height="312" alt="Screenshot 2026-11-24 085349" src="https://github.com/user-attachments/assets/f912dba5-2eac-4570-81aa-14c3e4011207" />



## Canny Edge Detector:


<img width="437" height="315" alt="Screenshot 2026-11-24 085415" src="https://github.com/user-attachments/assets/93365efb-32e8-4b8f-9faa-366845e3903a" />


## Hough Transform:


<img width="440" height="311" alt="Screenshot 2026-11-24 085431" src="https://github.com/user-attachments/assets/baeb1527-53a5-406b-a8d3-46d9fd27b48e" />


## Result

Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

---
