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
- Name:kishore S M
- Register Number:  212224230131

  ### Ex. No. 01

#### 1. Read the image ('kishore.jpg') using OpenCV imread() as a grayscale image.
```python
import cv2
import matplotlib.pyplot as plt
img = cv2.imread('KISHORE.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
plt.imshow(image_gray, cmap='gray')
plt.title("Grayscale Image")
plt.axis("off")
```

#### 2. Print the image width, height & Channel.
```python

image = cv2.imread('KISHORE.jpg')
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
```

#### 3. Display the image using matplotlib imshow().
```python

plt.imshow(img_rgb, cmap='viridis') 
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 4. Save the image as a PNG file using OpenCV imwrite().
```python
image = cv2.imread('KISHORE.jpg') 
img = cv2.imread('KISHORE.png',image)
```

#### 5. Read the saved image above as a color image using cv2.cvtColor().
```python
img = cv2.imread('KISHORE.jpg', cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
```

#### 6. Display the Colour image using matplotlib imshow() & Print the image width, height & channel.
```python
rectangle_img = cv2.rectangle(img_rgb, (0, 0), (768, 600), (0, 0, 255), 10)
plt.imshow(rectangle_img, cmap='viridis')  
plt.title("Image with Rectangle")
plt.axis('off')  
plt.show()
```

#### 7. Crop the image to extract any specific object from the image.
```python
crop = img_rgb[0:600,200:550] 
plt.imshow(crop[:,:,::-1])
plt.title("Cropped Region")
plt.axis("off")
plt.show()
crop.shape
```

#### 8. Resize the image up by a factor of 2x.
```python
image = cv2.imread('KISHORE.jpg')
resized_image = cv2.resize(image, (1600// 2, 1200 // 2))
resized_image_rgb = cv2.cvtColor(resized_image, cv2.COLOR_BGR2RGB)
plt.imshow(resized_image_rgb)
plt.title("Resized Image (Half Size)")
plt.axis("off")
plt.show()
```

#### 9. Flip the cropped/resized image horizontally.
```python

image = cv2.imread('KISHORE.jpg')
flipped_horizontally = cv2.flip(image, 1)
plt.imshow(flipped_horizontally_rgb)
plt.title("Flipped Horizontally")
plt.axis("off")
```

#### 10. Read in the image ('Apollo-11-launch.jpg').
```python
img=cv2.imread('Apollo-11-launch.jpg',cv2.IMREAD_COLOR)
img_rgb = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
img_rgb.shape
plt.imshow(img_rgb, cmap='viridis')  
plt.title("Original Image")
plt.axis('off')  
plt.show()
```

#### 11. Add the following text to the dark area at the bottom of the image (centered on the image):
```python
text = cv2.putText(img_rgb, "Apollo 11 Saturn V Launch, July 16, 1969", (300, 700),cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 255, 255), 2)  
plt.imshow(text, cmap='gray')  
plt.title("New image")
plt.show()  

```

#### 12. Draw a magenta rectangle that encompasses the launch tower and the rocket.
```python
rect_color = (255,0,255)
cv2.rectangle(img_rgb, (400, 100), (800, 650), rect_color, 3)  
```

#### 13. Display the final annotated image.
```python
plt.title("Annotated image")
plt.imshow(img_rgb)
plt.show()
```

#### 14. Read the image ('Boy.jpg').
```python
img =cv2.imread('boy.jpg',cv2.IMREAD_COLOR)
img_rgb= cv2.cvtColor(img, cv2.COLOR_BGR2RGB) 
```

#### 15. Adjust the brightness of the image.
```python
n = np.ones(img_rgb.shape, dtype="uint8") * 50
```

#### 16. Create brighter and darker images.
```python
img_brighter = cv2.add(img, matrix)
img_darker = cv2.subtract(img, matrix)
```

#### 17. Display the images (Original Image, Darker Image, Brighter Image).
```python
# YOUR CODE HERE
```

#### 18. Modify the image contrast.
```python
matrix1 = np.ones(img_rgb.shape, dtype="float32") * 1.1
matrix2 = np.ones(img_rgb.shape, dtype="float32") * 1.2
img_higher1 = cv2.multiply(img.astype("float32"), matrix1).clip(0,255).astype("uint8")
img_higher2 = cv2.multiply(img.astype("float32"), matrix2).clip(0,255).astype("uint8")
```

#### 19. Display the images (Original, Lower Contrast, Higher Contrast).
```
plt.figure(figsize=(10,5))
plt.subplot(1,3,1), plt.imshow(img), plt.title("Original Image"), plt.axis("off")
plt.subplot(1,3,2), plt.imshow(img_higher1), plt.title("Higher Contrast (1.1x)"), plt.axis("off")
plt.subplot(1,3,3), plt.imshow(img_higher2), plt.title("Higher Contrast (1.2x)"), plt.axis("off")
plt.show()
```

#### 20. Split the image into the B,G,R components & Display the channels.
```python
image_hsv_to_rgb = cv2.cvtColor(image_hsv, cv2.COLOR_HSV2RGB)
plt.imshow(image_hsv_to_rgb)
plt.title("HSV to RGB Image")
plt.axis("off")
```

#### 21. Merged the R, G, B , displays along with the original image
```python
image = cv2.imread('KISHORE.jpg')
plt.imshow(image_rgb)
plt.title("Original RGB Image")
plt.axis("off")
```

#### 22. Split the image into the H, S, V components & Display the channels.
```python
image_hsv = cv2.cvtColor(image_rgb, cv2.COLOR_RGB2HSV)
plt.imshow(image_hsv)
plt.title("HSV Image")
plt.axis("off")
```
#### 23. Merged the H, S, V, displays along with original image.
```python
merged_hsv = cv2.cvtColor(img, cv2.COLOR_HSV2RGB)
combined = np.concatenate((img_rgb, merged_hsv), axis=1)
plt.figure(figsize=(10, 5))
plt.imshow(combined)
plt.title("Original Image  &  Merged HSV Image")
plt.axis("off")
plt.show()
```

## Output:
- **i)** Read and Display an Image.
- <img width="399" height="520" alt="image" src="https://github.com/user-attachments/assets/3efbf6ef-5344-4ea1-9197-b7336e88f826" />

- <img width="384" height="570" alt="image" src="https://github.com/user-attachments/assets/16eaf5c7-eb7f-4e47-8ab4-3b99c57fd0bb" />
<img width="399" height="520" alt="image" src="https://github.com/user-attachments/assets/d76d75d3-8a06-4365-9c56-fca811594625" />

<img width="782" height="569" alt="image" src="https://github.com/user-attachments/assets/2ce12f24-9afa-444d-99bb-f9760c01cfc5" />

<img width="664" height="415" alt="image" src="https://github.com/user-attachments/assets/1fd945be-4725-4064-a982-ba55da8c6abb" />
<img width="805" height="555" alt="image" src="https://github.com/user-attachments/assets/e9ece4c9-3f80-4a35-8778-ca89c9a1d73a" />



- **ii)** Adjust Image Brightness.
-  <img width="827" height="244" alt="420662698-f34966ee-21f9-4441-bdd4-36c3da71b89d" src="https://github.com/user-attachments/assets/71c8bf69-5faa-45dc-a6d5-25c099f9d924" />


- **iii)** Modify Image Contrast.
-  <img width="835" height="228" alt="420662827-998698a5-0d84-4f73-96d6-68421a529951" src="https://github.com/user-attachments/assets/653f919d-04de-48f2-a531-30b2bb80b4a7" />
<img width="1498" height="1198" alt="image" src="https://github.com/user-attachments/assets/438f13fc-2143-416c-b0ef-2f19aefc2c58" />

- **iv)** Generate Third Image Using Bitwise Operations.
- 
<img width="771" height="382" alt="image" src="https://github.com/user-attachments/assets/e7ece0f0-33d2-43b9-92f1-b7731b4f486e" />
<img width="917" height="482" alt="image" src="https://github.com/user-attachments/assets/a914561f-64a7-4fdb-ba33-6e4a5c35ef41" />


## Result:
Thus, the images were read, displayed, brightness and contrast adjustments were made, and bitwise operations were performed successfully using the Python program.

