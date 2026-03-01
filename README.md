# Object-Detection with YOLOv8
Project Overview

This project explores object detection fundamentals through:

Manual implementation of Intersection over Union (IoU)

Object detection using YOLOv8 pretrained models

Video-based inference

Bounding box evaluation

The objective is to understand both the mathematical foundations and practical deep learning implementation of object detection systems.

Part 1: Intersection over Union (IoU)
Definition

Intersection over Union (IoU) measures the overlap between two bounding boxes.

IoU = Intersection Area / Union Area

It is widely used to evaluate object detection performance.

Implementation

The function calculate_iou(box1, box2):

Computes intersection coordinates

Calculates intersection area

Computes union area

Returns IoU score

Handles edge cases (no overlap or zero-area boxes)

Example:

box_A = [50, 50, 150, 150]
box_B = [100, 100, 200, 200]
box_C = [200, 200, 300, 300]

Expected behavior:

IoU(A, B) > 0 (overlapping boxes)

IoU(A, C) = 0 (no overlap)

Part 2: YOLOv8 Video Object Detection
Model

Pretrained YOLOv8 models were used:

yolov8n.pt (lightweight, faster)

yolov8s.pt (higher accuracy)

Video Input

manu_vs_athletic.mp4

Inference Example
model.predict(
    source=video,
    save=True,
    conf=0.5,
    iou=0.5,
    stream=True
)

Parameters:

conf: confidence threshold

iou: IoU threshold for Non-Maximum Suppression

save: saves annotated output

stream: memory-efficient processing

Dependencies

Install required packages:

pip install ultralytics opencv-python

For video processing in Linux/Colab:

apt-get install ffmpeg
Output

YOLO saves annotated results in:

runs/detect/predict/

The output includes:

Processed video with bounding boxes

Confidence scores per detection

Key Concepts Covered

Bounding box coordinate systems

Intersection over Union

Confidence thresholds

Non-Maximum Suppression (NMS)

Real-time video inference

Model size vs performance trade-off

Possible Extensions

Measure FPS and runtime performance

Compare yolov8n vs yolov8s quantitatively

Add object tracking

Evaluate detection quality using mAP

Conclusion

This project integrates theoretical evaluation (IoU) with practical object detection using YOLOv8. It demonstrates understanding of both evaluation metrics and modern deep learning-based detection pipelines.
