# EXP-2-Record-Image-Acquisition-using-Web-Camera


# Aim:
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file

Display the video

Display the video by resizing the window

Rotate and display the video

# Software Used :
Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

# Algorithm:
Step 1: Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2: Capture frames continuously from the webcam.

Step 3: Save a frame as a JPG image using cv2.imwrite().

Step 4: Display the live video stream using cv2.imshow().

Step 5: Resize the frame and rotate it using OpenCV functions, then display the processed frames.

# Program:
Developed By: Name:R ABHINAV GURU R

Register No:212225040009

i) Write the frame as JPG image
```
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
ii) Display the video
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
iii) Display the video by resizing the window
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
iv) Rotate and display the video
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
# Output:

# Result:
<img width="766" height="612" alt="image" src="https://github.com/user-attachments/assets/8015c147-1b40-4b7c-9e21-43cf31c8728f" />

<br>
<img width="770" height="582" alt="image" src="https://github.com/user-attachments/assets/4c5c72ff-8dfc-4dfc-ba8f-7e0b4518490d" />

<br>
<img width="401" height="581" alt="image" src="https://github.com/user-attachments/assets/f6811213-b5ef-4eeb-8af5-22048d701406" />
<br>
<img width="447" height="580" alt="image" src="https://github.com/user-attachments/assets/efbca5b5-2ad7-4c99-b54f-3a9f03061ee4" />




# Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
