# Image-Acquisition-from-Web-Cameraa
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
Use cv2.VideoCapture(0) to access web camera
<br>

### Step 2:
Use cv2.imread to read the video or image
<br>

### Step 3:
Use cv2.imwrite to save the image
<br>

### Step 4:
Use cv2.imshow to show the video
<br>

### Step 5:
End the program and close the output video window by pressing 'q'.
<br>

## Program:
#### Developed By: ARUN KUMAR SUKDEV CHAVAN
#### Register No: 212222230013
```python
# i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("trialer.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```


```python
# ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```

```python
# iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```


```python
# iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image

![exp2 1](https://github.com/arunkumarsukdevchavan/Image_Acqusition-_using_Web_Camera/assets/118343978/f38e3ad7-7e36-4001-b5c2-27b54762b36d)


</br>
</br>


### ii) Display the video
![exp2 2](https://github.com/arunkumarsukdevchavan/Image_Acqusition-_using_Web_Camera/assets/118343978/3c42853d-5336-4d48-bba1-8e9e3f89d17c)


</br>
</br>


### iii) Display the video by resizing the window

![exp2 3](https://github.com/arunkumarsukdevchavan/Image_Acqusition-_using_Web_Camera/assets/118343978/02635e98-6f50-4b6f-a112-f749cdc8077b)

</br>
</br>



### iv) Rotate and display the video
![exp2 4](https://github.com/arunkumarsukdevchavan/Image_Acqusition-_using_Web_Camera/assets/118343978/b46d425e-4a60-483a-a228-bb8eb9a080c1)


</br>
</br>


## Result 
Thus the image is accessed from webcamera and displayed using openCV.
