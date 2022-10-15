# 😱 OpenCV Face Recognition For Colab 😱
This repo is meant for those who prefer to use Google Colab for programming and AI development. Follow the instruction below to get up and running.

**Step 1:** Create a new Colab file and run the command in the first cell:

```!git clone https://github.com/virajdas/ColabFaceRecognition-OpenCV/```

**Step 2:** Click shift enter and then in the next cell copy and paste the following:

```
import cv2
from matplotlib import pyplot as plt
%matplotlib inline

cascade = cv2.CascadeClassifier("ColabFaceRecognition-OpenCV/haarcascade_frontalface_default.xml")
img = cv2.imread("ColabFaceRecognition-OpenCV/me.jpg")
img = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
faces = cascade.detectMultiScale(gray)
for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x+w, y+h), (255, 255, 0), 3)
    cv2.putText(img, "Face Detected", (x, y - 10), 1, 1.5, (255, 255, 255), 2)

plt.imshow(img)
```

Run it just to test. If you see a picture of Dwayne Johnson with the AI detecting his face you may move on.

**Step 3:** Remove the existing *me.jpg* file within the *ColabFaceRecognition-OpenCV* folder and take a picture of yourself or another person, name it: *me.jpg*, and upload it under the same folder as the old *me.jpg*.

Hopefully you now have a working AI face recognition script in Google Colab! 😉
