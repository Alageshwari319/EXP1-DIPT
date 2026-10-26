# EXP NO: 01 - IMAGE HANDLING AND PIXEL TRANSFORMATION USING OPENCV
## NAME: ALAGESHWARI V
## REG N0: 212224240010
## DATE: 23/10/2026

## AIM:
To perform image handling and pixel transformations using OpenCV by loading, displaying, converting, and manipulating images through pixel-level operations.


## PROCEDURE:

### Step1:
Load an image from your local directory and display it.
### Step2:
o Draw a line from the top-left to the bottom-right of the image.

o Draw a circle at the center of the image. 

o Draw a rectangle around a specific region of interest in the image. 

o Add the text "OpenCV Drawing" at the top-left corner of the image.
### Step3:
o Convert the image from RGB to HSV and display it.
    
o Convert the image from RGB to GRAY and display it. 

o Convert the image from RGB to YCrCb and display it. 
    
o Convert the HSV image back to RGB and display it.
### Step4:
o Access and print the value of the pixel at coordinates (100, 100). 

o Modify the color of the pixel at (200, 200) to white.
### Step5:
o Resize the original image to half its size and display it.
### Step6:
o Crop a region of interest (ROI) from the image (e.g., a 100x100 pixel area starting at (50, 50)) and display it.
### Step7:
o Flip the original image horizontally and display it. 

o Flip the original image vertically and display it.
### Step8:
o Save the final modified image to your local directory.

## CODE:
```python
import cv2
import matplotlib.pyplot as plt
# Read the image using OpenCV
img = cv2.imread('me.jpeg', cv2.IMREAD_COLOR)
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
# Display the image using Matplotlib
plt.imshow(img_rgb, cmap='viridis')  # You can change 'viridis' to another cmap or use None for RGB images
plt.title("Original Image")
plt.axis('off')  # Removes axis ticks and labels
plt.show()

# Load the image
image = cv2.imread('me.jpeg')
# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
# Draw a line from top-left to bottom-right
line_img = cv2.line(img_rgb, (0, 0), (768, 600), (255, 0, 0), 2) # cv2.line(image, start_point, end_point, color, thickness)
plt.imshow(line_img, cmap='viridis')  
plt.title("Image with Line")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('Qno. 1.jpg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
circle_img = cv2.circle(img_rgb,(170,150),150,(255,0,5),10) # cv2.circle(image, center, radius, color, thickness)
plt.imshow(circle_img, cmap='viridis')  
plt.title("Image with Circle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('me.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

img.shape
# Draw a rectangle around the Whole image
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (330, 300), (0, 0, 255), 10)  # cv2.rectangle(image, start_point, end_point, color, thickness)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()

# Load the image
image = cv2.imread('me.jpeg') 

# Convert BGR (OpenCV's default) to RGB (Matplotlib's expected color order)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

# Add text to the image
text_img = cv2.putText(img_rgb, "ALAGESHWARI V", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (0, 0, 0), 10)  ## cv2.putText(image, text, position, font, font_scale, color, thickness)
plt.imshow(text_img, cmap='viridis')  
plt.title("Image with Text")
plt.axis('off')  
plt.show()
# Load the image
image = cv2.imread('me.jpeg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Original RGB Image
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
# Convert RGB to HSV
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
# HSV Image
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
# Convert RGB to GRAY
image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
# Grayscale Image
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
# Convert RGB to YCrCb
image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
# YCrCb Image
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
# Convert HSV back to RGB
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
# Modify a block of pixels (300x300) to white, starting from (200, 200)
image[100:300, 100:300] = [255, 255, 255]  # Rows: 200-499, Columns: 200-499
# Convert BGR to RGB for displaying with Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
# Display the modified image
plt.imshow(image_rgb)
plt.title("Image with 300x300 White Block")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('me.jpeg')
image.shape
# Resize the image to half its size
resized_image = cv2.resize(image, (768 // 2, 600 // 2))  # (new_width, new_height)
# Convert BGR to RGB for displaying with Matplotlib
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
resized_image_rgb.shape
# Display the resized image
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('me.jpeg')
image.shape
# Crop a 300x300 region starting from (50, 50)
roi = image[50:350, 50:350]  # Rows: 50-349, Columns: 50-349
# Convert BGR to RGB for displaying with Matplotlib
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)
# Display the cropped region (ROI)
plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()
# Load the image
image = cv2.imread('me.jpeg') 
# Flip the image horizontally (left-right)
flipped_horizontally = cv2.flip(image, 1)
# Convert BGR to RGB for displaying with Matplotlib
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)
# Horizontal flip
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
# Flip the image vertically (up-down)
flipped_vertically = cv2.flip(image, 0)
# Convert BGR to RGB for displaying with Matplotlib
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)
# Vertical flip
plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
```

## OUTPUT:

<img width="360" height="500" alt="image" src="https://github.com/user-attachments/assets/4ac7d365-125d-4f01-bd8b-4646ed47455f" />

<img width="358" height="496" alt="image" src="https://github.com/user-attachments/assets/45d263ae-5678-4e55-8c2e-efb462361ab8" />

<img width="358" height="492" alt="image" src="https://github.com/user-attachments/assets/89ec4bac-8f7f-493a-8556-7c3356475351" />

<img width="361" height="501" alt="image" src="https://github.com/user-attachments/assets/a06e3982-4523-4d78-9e8d-9aca45d5898c" />

<img width="356" height="498" alt="image" src="https://github.com/user-attachments/assets/f2d78a3c-04d0-441c-9401-4c672b2258f9" />

<img width="710" height="532" alt="image" src="https://github.com/user-attachments/assets/3b90bfb3-7ee0-4f16-b48c-c296432f61c1" />


<img width="680" height="530" alt="image" src="https://github.com/user-attachments/assets/3e36fddd-1d78-4b3f-b7bd-271aeb7fb1f0" />




<img width="695" height="527" alt="image" src="https://github.com/user-attachments/assets/c44e1303-2a3c-4cf6-a814-21cacd265f04" />



<img width="677" height="531" alt="image" src="https://github.com/user-attachments/assets/db23e2b7-359c-4542-99c4-9ba69c182581" />


<img width="666" height="526" alt="image" src="https://github.com/user-attachments/assets/538643b5-af1b-482e-a65d-d7813efa6f59" />




<img width="360" height="497" alt="image" src="https://github.com/user-attachments/assets/9790388a-623d-401c-98d3-15a7956e2d8a" />



<img width="435" height="370" alt="image" src="https://github.com/user-attachments/assets/4c8b84cd-79cf-4a7e-9720-02e5c7329523" />


<img width="436" height="492" alt="image" src="https://github.com/user-attachments/assets/3ef13d17-82b3-4ed3-898b-bc8b907959e1" />



<img width="685" height="531" alt="image" src="https://github.com/user-attachments/assets/2df1570d-f68c-4a14-a0d7-e2a584c4aa0b" />



<img width="680" height="520" alt="image" src="https://github.com/user-attachments/assets/dd1d0e9b-7454-4c95-b03a-29f34e16ee20" />

## RESULT:

Thus the Image Handling and Pixel Transformation Using Opencv was verified successfully.

