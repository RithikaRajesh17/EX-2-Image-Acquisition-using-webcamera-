# Ex.-No-02-Image-Acquisition-using-Web-Camera

## Aim
```
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:
1.Write the frame as a JPG file
2.Display the video
3.Display the video by resizing the window
4.Rotate and display the video
```
## Software Used
```
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
```
## Algorithm
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

## Program
~~~py
Developed By:
Name: Rithika R
Register No:212224240136

##i) Write the frame as JPG file
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

##ii) Display the video
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

##iii) Display the video by resizing the window

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

##iv) Rotate and display the video
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



~~~
## Output
i) Write the frame as JPG image

<img width="617" height="467" alt="image" src="https://github.com/user-attachments/assets/38bebecb-43b9-4c9c-86e8-613fdb140d4f" />

Captured image is saved as captured_image.jpg

ii) Display the video

<img width="610" height="460" alt="image" src="https://github.com/user-attachments/assets/d93f1864-8f06-416d-8eee-06bf993ab281" />

Live webcam video is displayed

iii) Display the video by resizing the window

<img width="301" height="457" alt="image" src="https://github.com/user-attachments/assets/51892822-1ccc-43d4-824f-631725b04afc" />

Video is shown in resized resolution (640 × 480)

iv) Rotate and display the video

<img width="347" height="461" alt="image" src="https://github.com/user-attachments/assets/0c04073a-96cb-4705-8a4e-36d080d417cd" />

Video is displayed after rotation (90° clockwise)

## Result
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
