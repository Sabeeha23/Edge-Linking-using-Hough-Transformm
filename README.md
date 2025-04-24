# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## Program 
## Developed by : Sabeeha Shaik
## Register Number : 212223230176

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('ocean.jpg')
```
```
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
```

```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```

```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  # Unpacking the line coordinates
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```


## Output

### Input image and grayscale image
![image](https://github.com/user-attachments/assets/dfb537b9-df78-4a96-a31e-d5e1e8a7141f)

### Grayscale

![image](https://github.com/user-attachments/assets/547f2ea8-3f26-4b94-be64-abe44ed9d41f)



### Canny Edge detector output
![image](https://github.com/user-attachments/assets/89fcae46-9c7e-4706-90c1-3c280bf554d5)

### Display the result of Hough transform

![image](https://github.com/user-attachments/assets/836b9f7b-e6ba-41d7-953d-8dc5e937e4c8)

## Result

Thus,The Python program to detect the lines using Hough Transform run successfully.


