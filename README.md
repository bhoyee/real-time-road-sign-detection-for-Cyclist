# This is a Real-time Road Sign Detection and Recognition for Cyclists using Deep Learning

# This is Real-Time Object Detection with YOLOv4 and Text-to-Speech Notifications


This project demonstrates real-time object detection using YOLOv4 and provides text-to-speech notifications when road signs are detected. The code includes steps for gathering a custom dataset, labeling the dataset, training the YOLOv4 model using Darknet, and running real-time object detection.

Prerequisites
Python 3.x
OpenCV (pip install opencv-python)
NumPy (pip install numpy)
pyttsx3 (pip install pyttsx3)
Darknet (Follow the instructions in the Darknet repository: https://github.com/AlexeyAB/darknet)

## Setup

1. Download the YOLOv4 model files:
   - Download the `yolov4_custom_1.cfg` and `yolov4_custom_12000.weights` files for the custom trained YOLOv4 model.
   - Place the files in the same directory as the code.

2. Install the required dependencies:
   - Install OpenCV by running `pip install opencv-python`.
   - Install NumPy by running `pip install numpy`.
   - Install pyttsx3 by running `pip install pyttsx3`.

## Usage

1. Run the script using `python <filename.py>`.
2. The PC camera will open, and the video stream will start.
3. The script will detect road signs in real-time and display the processed video frames with bounding boxes and labels.
4. When road signs are detected, a text-to-speech notification will be spoken, announcing the type of sign(s) detected.
5. To exit the program, press the 'q' key.

Note: If you have multiple cameras connected, you can change the camera index in the `handle_video_stream` function by modifying the `cap = cv2.VideoCapture(0)` line. Set the appropriate index for your camera (e.g., 0 for the first camera, 1 for the second camera, and so on).

## Customization

- If you want to use a different YOLOv4 model, replace the `yolov4_custom_1.cfg` and `yolov4_custom_12000.weights` files with the corresponding model files.
- Modify the `classes` list to match the class labels used in your custom YOLOv4 model.
- Adjust the confidence threshold and other parameters in the `detect_objects` function to change the object detection sensitivity.

Feel free to modify the code to suit your specific requirements and customize the behavior of the object detection and notification system.