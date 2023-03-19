# Image-Acquisition-from-Web-Camera
## Aim
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
### Step 1:
Use VideoCapture(0) to access web camera.

### Step 2:
Use imread to read the video or image.

### Step 3:
Use imshow to show the video.

### Step 4:
Use imshow to show the video.

### Step 5:
End the program and close the output video windows by pressing 'q'.

## Program:
``` Python
## Developed By: Dineshkumar S
## Register Number: 212220230012

## i) Write the frame as JPG file
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("apple.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()

## ii) Display the video
import cv2
import numpy as np
obj = cv2.VideoCapture(0)
while True:
    ret,frame = obj.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window
import cv2
import numpy as np
cap=cv2.VideoCapture(0)

while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iv) Rotate and display the video
import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![Screenshot (37)](https://user-images.githubusercontent.com/75234807/165555638-898ac7c7-af27-4966-9e07-0645db647248.png)

### ii) Display the video
![Screenshot (34)](https://user-images.githubusercontent.com/75234807/165553807-b81eb196-c0ab-49b7-98c5-9912559ffbfc.png)

### iii) Display the video by resizing the window
![Screenshot (35)](https://user-images.githubusercontent.com/75234807/165553872-bfb25e27-b35f-4009-8fa5-1dddba9b4ae1.png)

### iv) Rotate and display the video
![Screenshot (36)](https://user-images.githubusercontent.com/75234807/165555686-b3ea07dd-4e01-4c11-b9e3-880d22c0a8c8.png)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
