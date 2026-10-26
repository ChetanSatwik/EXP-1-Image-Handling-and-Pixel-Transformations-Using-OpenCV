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
- **Name:** N V Chetan Satwik 
- **Register Number:** 212224240100

  ### Ex. No. 01
```python
import cv2
import matplotlib.pyplot as plt

img = cv2.imread('1sample.png', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)

plt.imshow(img_rgb)
plt.title("Original Image")
plt.axis('off')
plt.show()


image = cv2.imread('1sample.png')
img_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

line_img = cv2.line(img_rgb.copy(), (0, 0), (image.shape[1] - 1, image.shape[0] - 1), (255, 0, 0), 2)
plt.imshow(line_img)
plt.title("Image with Line")
plt.axis('off')
plt.show()

circle_img = cv2.circle(img_rgb.copy(), (image.shape[1] // 2, image.shape[0] // 2), 150, (255, 0, 0), 10)
plt.imshow(circle_img)
plt.title("Image with Circle")
plt.axis('off')
plt.show()

rectangle_img = cv2.rectangle(img_rgb.copy(), (0, 0), (image.shape[1] - 1, image.shape[0] - 1), (0, 0, 255), 10)
plt.imshow(rectangle_img)
plt.title("Image with Rectangle")
plt.axis('off')
plt.show()

text_img = cv2.putText(img_rgb.copy(), "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)
plt.imshow(text_img)
plt.title("Image with Text")
plt.axis('off')
plt.show()


image = cv2.imread('1sample.png')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
plt.show()

image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
plt.show()

image_gray = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2GRAY)
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
plt.show()

image_ycrcb = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2YCrCb)
plt.imshow(image_ycrcb)
plt.title("YCrCb Image")
plt.axis("off")
plt.show()

image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
plt.show()


image = cv2.imread('1sample.png')

print("Pixel value at (100, 100):", image[100, 100])

image[200, 200] = [255, 255, 255]
image[200:500, 200:500] = [255, 255, 255]

image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Modified Image")
plt.axis("off")
plt.show()


image = cv2.imread('1sample.png')

height, width = image.shape[:2]
resized_image = cv2.resize(image, (width // 2, height // 2))
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)

plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()


image = cv2.imread('1sample.png')

roi = image[50:150, 50:150]
roi_rgb = cv2.cvtColor(roi, cv2.COLOR_BGR2RGB)

plt.imshow(roi_rgb)
plt.title("Cropped Region of Interest (ROI)")
plt.axis("off")
plt.show()


image = cv2.imread('1sample.png')

flipped_horizontally = cv2.flip(image, 1)
flipped_horizontally_rgb = cv2.cvtColor(flipped_horizontally, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
plt.show()

flipped_vertically = cv2.flip(image, 0)
flipped_vertically_rgb = cv2.cvtColor(flipped_vertically, cv2.COLOR_BGR2RGB)

plt.imshow(flipped_vertically_rgb)
plt.title("Flipped Vertically")
plt.axis("off")
plt.show()


image = cv2.imread('1sample.png')

cv2.rectangle(image, (0, 0), (image.shape[1] - 1, image.shape[0] - 1), (0, 0, 255), 10)
cv2.putText(image, "OpenCV Drawing", (10, 30), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)

cv2.imwrite('final_modified_image.png', image)

print("Image saved successfully!")
```


## Output:
<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/e77764d3-fb67-4d38-ad3a-aebc8fd7e704" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/8afd6054-218d-4f13-a24d-cc7555777c8b" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/7229bbb4-d5fc-4c94-8230-29fe00636903" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/bd13d75f-7b42-4b80-8bcd-68403e5f75c7" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/38b7a328-54e9-4207-9386-10bfc32e6e9b" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/8bf57a0f-9d37-4ed9-a2ea-de37eac76d12" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/32342cb5-31dc-424b-bbe4-3a86feef67a9" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/2b5b8abc-7767-479d-8e19-8379cf207049" /><br>


<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/cf0be2af-11e3-4c47-9afa-09e0751f0cb1" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/2f83db3d-18ed-4714-8923-e49a11106944" /><br>


<img width="302" height="410" alt="download" src="https://github.com/user-attachments/assets/f9fb84e4-bd78-4829-b994-1bcb139e25ca" /><br>


<img width="493" height="410" alt="download" src="https://github.com/user-attachments/assets/a663c634-13f2-427d-b10e-bf5f034dea38" /><br>


<img width="389" height="410" alt="download" src="https://github.com/user-attachments/assets/e0008b40-f269-443f-a3da-c74e5ace2d28" /><br>


<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/be5c2f20-5f72-4464-8de4-18374094c9b7" /><br>

<img width="296" height="410" alt="download" src="https://github.com/user-attachments/assets/6f2beaba-f12c-4463-a3bf-ba81ec0504a0" />


- **i)** Read and Display an Image.  
- **ii)** Adjust Image Brightness.  
- **iii)** Modify Image Contrast.  
- **iv)** Generate Third Image Using Bitwise Operations.

## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.
