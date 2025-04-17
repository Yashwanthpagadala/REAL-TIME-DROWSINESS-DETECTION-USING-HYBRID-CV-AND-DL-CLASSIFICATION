REAL-TIME DROWSINESS DETECTION USING HYBRID CV AND DL CLASSIFICATION
=====================================================================

Project Overview:
-----------------
This project implements a real-time driver drowsiness and yawn detection system using a hybrid approach that combines classical computer vision techniques with deep learning-based facial landmark detection.

The system alerts the driver using:
- Alarm sounds
- Danger alerts
- Yawn detection
- Twilio SMS notification

Key Features:
-------------
- Real-time face, eye, and lip tracking
- Eye Aspect Ratio (EAR) based drowsiness detection
- Lip distance-based yawn detection
- Color-coded visual alerts (green, yellow, red)
- Sound alarms (regular, danger, yawn)
- SMS alert using Twilio API
- Dataset with annotated training and testing frames of driver expressions

Dependencies:
-------------
Install the required Python packages:
```
!pip install numpy
!pip install imutils
!pip install scipy
!pip install dlib
!pip install twilio
!pip install opencv-python
!pip install "path_to\dlib-19.24.99-cp312-cp312-win_amd64.whl"
```

Other Requirements:
-------------------
- shape_predictor_68_face_landmarks.dat
- haarcascade_frontalface_default.xml
- alarm.wav
- yawn_sound.wav
- Danger.wav

Directory Structure:
--------------------
DROWSINESS_AND_YAWN_DETECTION/
│
├── main.py                       # Main execution script
├── shape_predictor_68_face_landmarks.dat
├── haarcascade_frontalface_default.xml
├── alarm.wav
├── yawn_sound.wav
├── Danger.wav
├── dlib-19.24.99-cp312-cp312-win_amd64.whl
├── dataset/
│   ├── train_frames/
│   └── test_frames/
└── README.txt

How to Run:
-----------
1. Clone or download the repository.
2. Install all dependencies as listed above.
3. Make sure the required `.dat` and `.xml` files and audio files are present in the correct directory.
4. Execute the script using:
```
python main.py
```

Working:
--------
- The webcam starts automatically.
- Detects the driver’s face and tracks eyes/lips using dlib.
- Calculates EAR (Eye Aspect Ratio) and lip distance.
- Issues different alerts depending on drowsiness level:
    • Yellow alert (mild drowsiness)
    • Red alert (prolonged drowsiness)
    • Yawn alert
- Sends SMS when severe drowsiness is detected.

Visual Examples:
----------------
1. **Alert SMS Notification Example:**
   ![Alert SMS](https://i.ibb.co/2JDdH7k/sms-alert.png)

2. **Sample Input Frame of Driver:**
   ![Sample Driver Input](https://i.ibb.co/y9nzTpr/sample-frame.png)

Twilio Integration:
-------------------
To enable SMS alerts:
- Replace `ACCOUNT_SID`, `AUTH_TOKEN`, `TWILIO_PHONE_NUMBER`, and `TO_PHONE_NUMBER` in the `twilo_msg()` function with your credentials.

Contact:
--------
For any queries or contributions, feel free to raise an issue or pull request.

License:
--------
This project is licensed under the MIT License.
