## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations. i) Write the frame as JPG ii) Display the video iii) Display the video by resizing the window iv) Rotate and display the video

Software Used
Anaconda - Python 3.7

## Algorithm
Step 1:
Import OpenCV Package.

Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.

Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.

## Program
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("Sharon.jpg", frame)
cap.release()
captured_image = cv2.imread('Sharon.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.axis('off')
plt.show()
```
## output
<img width="512" height="409" alt="f8cbb45f-7aae-4b76-85a5-4e7cac6d40c1" src="https://github.com/user-attachments/assets/fac54182-d3da-45d6-913b-6e654babdf03" />

## program
```
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
## output
<img width="512" height="389" alt="5b2c258d-297d-4de5-a9b8-5e8c4cd1d680" src="https://github.com/user-attachments/assets/dba39ea2-c068-4658-8790-09544cb7aa9c" />

## program
```

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
## output
<img width="266" height="389" alt="78b87250-3b7e-4edf-9548-019db43b0e33" src="https://github.com/user-attachments/assets/18dc0e0f-82e9-46ea-a6bb-14dacda156c5" />

## program
```
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
## output
<img width="297" height="389" alt="1b05dca8-b6d7-4bc3-b13d-2f7a0b2f71ee" src="https://github.com/user-attachments/assets/f7656220-9b9d-4c11-a154-03c286deab67" />

## Result
Thus the image is accessed from webcamera and displayed using openCV.







