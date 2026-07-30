# Image Capture and Video Processing Using OpenCV

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  


## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.



## 💻 Program

### Developed By:
##### Name: MAGESH BOOPATHI.M

#### Register No: 212224230145


### i) Write the frame as JPG image
```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```
## Output
<img width="732" height="525" alt="Screenshot 2026-07-30 085843" src="https://github.com/user-attachments/assets/e6df1762-ac81-4d3c-996f-f9cb29bd1762" />


### ii) Display the video

```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
## Output

<img width="725" height="511" alt="Screenshot 2026-07-30 085849" src="https://github.com/user-attachments/assets/50a869db-00af-4bc3-ba33-ea7f7a9e2f26" />

### iii) Display the video by resizing the window
```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
## Output
<img width="547" height="509" alt="Screenshot 2026-07-30 085858" src="https://github.com/user-attachments/assets/4d0261a0-4410-4e45-97da-1a327b31ed66" />

### iv) Rotate and display the video
```python
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
## Output
<img width="444" height="526" alt="Screenshot 2026-07-30 085904" src="https://github.com/user-attachments/assets/bfcba237-0b92-40e4-9ceb-b5864f536fdb" />


## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
