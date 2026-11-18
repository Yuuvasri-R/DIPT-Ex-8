# Image Segmentation Using Thresholding Techniques in OpenCV

# Aim
To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

Global Thresholding
Adaptive Thresholding
Otsu's Thresholding
Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

# Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Load the input image using OpenCV.

Step 3:
Convert the input image into grayscale format.

Step 4: Global Thresholding
Select a fixed threshold value.
Apply thresholding to separate foreground and background pixels.
Display the thresholded image.

Step 5: Adaptive Thresholding
Compute threshold values for small regions of the image.
Apply Adaptive Mean Thresholding.
Apply Adaptive Gaussian Thresholding.
Display the segmented images.

Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.
Apply Otsu's thresholding technique.
Display the segmented image.

Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

Program
Developed By
Name: Yuuvasri R

Register No: 212225230313
```
import cv2
import matplotlib.pyplot as plt

# Read image in grayscale
img = cv2.imread("cat.png", cv2.IMREAD_GRAYSCALE)

# Check whether image is loaded
if img is None:
    print("Error: Image not found!")
else:
    # 1. Original Grayscale Image
    plt.figure(figsize=(12, 8))

    plt.subplot(2, 2, 1)
    plt.imshow(img, cmap="gray")
    plt.title("Original Grayscale Image")
    plt.axis("off")

    # 2. Global Thresholding
    _, global_result = cv2.threshold(
        img, 127, 255, cv2.THRESH_BINARY
    )

    plt.subplot(2, 2, 2)
    plt.imshow(global_result, cmap="gray")
    plt.title("Global Thresholding")
    plt.axis("off")

    # 3. Adaptive Thresholding
    adaptive_result = cv2.adaptiveThreshold(
        img, 255,
        cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
        cv2.THRESH_BINARY,
        11, 2
    )

    plt.subplot(2, 2, 3)
    plt.imshow(adaptive_result, cmap="gray")
    plt.title("Adaptive Thresholding")
    plt.axis("off")

    # 4. Otsu's Thresholding
    _, otsu_result = cv2.threshold(
        img, 0, 255,
        cv2.THRESH_BINARY + cv2.THRESH_OTSU
    )

    plt.subplot(2, 2, 4)
    plt.imshow(otsu_result, cmap="gray")
    plt.title("Otsu's Thresholding")
    plt.axis("off")

    # Display all images
    plt.tight_layout()
    plt.show()

```
# OUTPUT: 
<img width="532" height="412" alt="image" src="https://github.com/user-attachments/assets/dd63620a-cf21-43cb-a20a-f8716a215745" />
<img width="527" height="412" alt="image" src="https://github.com/user-attachments/assets/ea99ba27-de08-478f-9a93-fab0d3b710cb" />
<img width="525" height="420" alt="image" src="https://github.com/user-attachments/assets/991468a5-d3c3-4db3-a7f6-c08b0dfd34d0" />
<img width="538" height="415" alt="image" src="https://github.com/user-attachments/assets/fc00f093-100b-4009-b965-84dde1228b1b" />

# Result
Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
