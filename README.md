# Real-Time Threat Detection using YOLOv8

This project implements a real-time threat detection system using **YOLOv8** (You Only Look Once) for object detection. The system uses a webcam feed to monitor for suspicious objects, and it triggers an alert when a suspicious object, such as a "knife," is detected. The system employs **Python**, **OpenCV**, and the **Ultralytics YOLO** model to detect objects and track activities in real-time.

## Features
- **Real-Time Monitoring**: Continuously captures video from the webcam.
- **Object Detection**: Utilizes YOLOv8 to detect objects from a list of predefined classes.
- **Suspicious Activity Detection**: Alerts when a suspicious object (e.g., "knife") is detected, triggering an immediate exit of the program.
- **Bounding Boxes**: Displays bounding boxes around detected objects with class labels and confidence scores.
  
## Requirements

- Python 3.x
- OpenCV
- Ultralytics YOLOv8 Model

## Example Output
> Image
<p align="center" width="100%">
    <img width="90%" src="https://github.com/dihitha-n/Realtime_Threat_Detection/blob/main/Images/ThreatDetectionOutput.PNG">
</p>
