# Image Acquisition using Web Camera

**Name:** S Sajetha
**Register Number:** 212223100049

## Aim :
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm :
### Step 1 :

Import the cv2 and numpy package.
<br>
### Step 2 :
Read the Video frame using the cv2.VideoCapture(0)
<br>

### Step 3 :
Write the image using imwrite().
<br>

### Step 4 :
Display the frame using the imshow().
<br>

### Step 5 :
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().
<br>

## Program :


## i) Write the frame as JPG file 

```python
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()


```



## ii) Display the video

```python

import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
cv2.destroyAllWindows()

```


## iii) Display the video by resizing the window

```python
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video

```python
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
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```








## Output :

### i) Write the frame as JPG image

![Screenshot 2025-06-01 211701](https://github.com/user-attachments/assets/72190568-2986-4459-a47d-34a01d9975ee)



</br>
</br>


### ii) Display the video

![Screenshot 2025-06-01 214041](https://github.com/user-attachments/assets/b5197930-ffcb-4217-aff9-2dfc56f09b6a)



</br>
</br>


### iii) Display the video by resizing the window


<img width="403" alt="Screenshot 2024-09-28 at 11 37 35 AM" src="https://github.com/user-attachments/assets/3f6390b8-9ac9-4915-bfa4-4008ce8d9b89">


</br>
</br>



### iv) Rotate and display the video

<img width="798" alt="Screenshot 2024-09-28 at 11 37 55 AM" src="https://github.com/user-attachments/assets/7dabd299-b9ae-4f37-bf72-993f83bbb96c">



</br>
</br>





## Result :
Thus the image is accessed from webcamera and displayed using openCV.
