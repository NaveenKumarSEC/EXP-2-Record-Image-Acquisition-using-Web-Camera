# EXP-2-Record-Image-Acquisition-using-Web-Camera

## Aim:
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file

2. Display the video

3. Display the video by resizing the window

4. Rotate and display the video


## Software Used:

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

## Algorithm:

Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

## Program:

### Developed By:
### Name: Naveenkumar M
### Reg.No: 212224230182

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

## Output:

### i) Write the frame as JPG image
Captured image is saved as captured_image.jpg

<img width="512" height="410" alt="afeea65d-e486-47a9-9107-b0fcb87ed9da" src="https://github.com/user-attachments/assets/6d567b7d-2ed7-4d54-82f5-92ce1d9fa124" />


### ii) Display the video
Live webcam video is displayed

<img width="512" height="389" alt="cc632cd4-6f0c-4691-a8ae-5b0ab531b9a5" src="https://github.com/user-attachments/assets/ea22ae73-c009-496b-9d5c-808e9506a3b3" />


### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)

<img width="266" height="389" alt="6eb268c7-e645-4e46-83c1-59eb7dd358c6" src="https://github.com/user-attachments/assets/9cc1356b-22d1-479e-951e-7579fd47179a" />


### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)

<img width="297" height="389" alt="2dfac980-cc52-42b7-8b86-6b5f2b16033e" src="https://github.com/user-attachments/assets/c6701bcf-7e5b-4e85-8d2a-efbf346bf387" />


## Result:

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
