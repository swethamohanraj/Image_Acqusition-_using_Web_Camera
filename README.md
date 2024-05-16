<h1> ### EXP-02-Image_Acqusition using Web Camera </h1>

## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
<br>
i) Write the frame as JPG 
<br>
ii) Display the video
<br>
iii) Display the video by resizing the window
<br>
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0)
<br>

### Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame)
<br>

### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
<br>

### Step 4:
Display the image until the loop gets over
<br>

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
<br>

## Program:

## i) Write the frame as JPG file
``` python
Developed By:K.M.SWETHA
Register No:212221240055
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("NewPicture.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video
```python
import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```python
import numpy as np
import cv2

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
    image[height//2:, width//2:] = smaller_frame

    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```python
import numpy as np
import cv2

cap = cv2.VideoCapture(0)

while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    
    image = np.zeros(frame.shape, np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:,: width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame


    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```









## Output

### i) Write the frame as JPG image
![image](https://github.com/swethamohanraj/Image_Acqusition-_using_Web_Camera/assets/94228215/c4552c8a-ead5-41c6-937f-40c943693f54)



### ii) Display the video
![image](https://github.com/swethamohanraj/Image_Acqusition-_using_Web_Camera/assets/94228215/aa41c6e4-a04f-4e20-8961-239f2d86bd8b)


### iii) Display the video by resizing the window
![image](https://github.com/swethamohanraj/Image_Acqusition-_using_Web_Camera/assets/94228215/7d9ad409-9382-4cd1-ba3f-4b3fd675a3c4)




### iv) Rotate and display the video
![image](https://github.com/swethamohanraj/Image_Acqusition-_using_Web_Camera/assets/94228215/cc31611b-3496-4355-9d1e-384a8641e406)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
