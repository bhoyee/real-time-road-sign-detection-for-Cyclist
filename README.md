# This is a Real-time Road Sign Detection and Recognition for Cyclists using Deep Learning

# This is Real-Time Object Detection with YOLOv4 and Text-to-Speech Notifications


This project demonstrates real-time object detection using YOLOv4 and provides text-to-speech notifications when road signs are detected. The code includes steps for gathering a custom dataset, labeling the dataset, training the YOLOv4 model using Darknet, and running real-time object detection.

## Prerequisites
Python 3.x
OpenCV (pip install opencv-python)
NumPy (pip install numpy)
pyttsx3 (pip install pyttsx3)
Darknet (Follow the instructions in the Darknet repository: https://github.com/AlexeyAB/darknet)


## Dataset Gathering and Labeling

1. Gather a dataset of road sign images. This can be done by capturing images using a camera or collecting images from publicly available datasets.

2. Organize the dataset into separate folders for each class of road sign. For example, create a folder named `stop_sign` and place all the stop sign images inside it. Similarly, create folders for other classes such as `warning_sign`, `speed_limit`, etc.

3. Label the dataset using a labeling tool such as LabelImg ([https://github.com/tzutalin/labelImg](https://github.com/tzutalin/labelImg)). Open the tool, load an image, and draw bounding boxes around the road signs in the image. Save the labeled annotations in YOLO format, which consists of a text file for each image containing the class index and bounding box coordinates.

4. Split the dataset into training and validation sets. The typical split is around 80% for training and 20% for validation. Make sure both sets have a balanced distribution of classes.

## Training the YOLOv4 Model

1. Download the YOLOv4 repository from Darknet: [https://github.com/AlexeyAB/darknet](https://github.com/AlexeyAB/darknet).

2. Compile Darknet by following the instructions provided in the repository. Make sure to enable the GPU and OpenCV support.

3. Create a custom configuration file (`yolov4_custom.cfg`) based on the `yolov4.cfg` file provided in the Darknet repository. Modify the configuration file to match the number of classes, filters, and other settings specific to your dataset.

4. Create a text file (`custom_data.names`) listing the names of all the classes in your dataset, each on a separate line.

5. Create a text file (`custom_data.data`) specifying the paths to the training and validation data, class names file, backup directory, and other parameters.

6. Download the pre-trained weights for the YOLOv4 model: [https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.conv.137](https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.conv.137). Place the downloaded weights file in the Darknet directory.

7. Train the YOLOv4 model using the following command:
   ```
   ./darknet detector train custom_data.data yolov4_custom.cfg yolov4.conv.137 -map
   ```
   This command starts the training process with the custom dataset. The `-map` flag calculates the mean Average Precision (mAP) during training.

8. Monitor the training process and adjust parameters as needed. The

 training will save weights files periodically based on the `snapshot` and `backup` settings in the configuration file.

9. Once the training is complete and you have satisfactory results, select the final weights file generated in the `backup` directory for inference.

