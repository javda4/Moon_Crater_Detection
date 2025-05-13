# Moon_Crater_Detection
## YOLOv5, YOLOv8, and YOLOv12 Usage Guide

This repository provides instructions on how to use YOLOv5, YOLOv8, and YOLOv12 for object detection tasks, including training, validation, and inference.

### Table of Contents
- [Installation](#installation)
- [Training](#training)
- [Validation](#validation)
- [Inference](#inference)


---

### Installation

#### Clone and install Ultralytics
```bash
git clone https://github.com/ultralytics/yolov5.git

cd yolov5

pip install -r requirements.txt

pip install ultralytics

git clone https://github.com/ultralytics/ultralytics.git

cd ultralytics
```

### Training

Examples:
```bash
python train.py --img 640 --batch 16 --epochs 100 --data data.yaml --weights yolov5s.pt --name yolov5s_model

yolo task=detect mode=train model=yolov8s.pt data=data.yaml epochs=100 imgsz=640

yolo task=detect mode=train model=yolov12s.pt data=data.yaml epochs=100 imgsz=640
```

### Validation

Examples:
```bash
python val.py --weights runs/train/yolov5s_model/weights/best.pt --data data.yaml --img 640

yolo task=detect mode=val model=runs/detect/train/weights/best.pt data=data.yaml imgsz=640

yolo task=detect mode=val model=runs/detect/train/weights/best.pt data=data.yaml imgsz=640
```

### Inference

Examples:
```bash
python detect.py --weights yolov5s.pt --img 640 --source path/to/images_or_video

yolo task=detect mode=predict model=yolov8s.pt source=path/to/images_or_video imgsz=640

yolo task=detect mode=predict model=yolov12s.pt source=path/to/images_or_video imgsz=640
```

### Layout

Ultralytics1 is ultralytics just a localized version to account for github distribution chokepoints

To perform performing Yolov5 actions you must be in the yolov5 folder as it contains all the scripts and call to its scrpits needed to perform training, validation, and inference

For Yolov8 and Yolov12 with the pip installation of ultralytics and the ultralytics folder you have all the materials needed to use CLI to perform yolo tasks (training, validation, inference)

The folders yolov5_materials, yolov8_materials, and yolov12_materials contain the diversified (70-20-10 / training-validation-testing) image datasets and the data.yaml that stores the classes

Pretrained weights will automatically download to your device and be used for training if using a pretrained model to train a new model

yolov5_best.pt, yolov8_best.pt, and yolov12_best.pt were our custom made moon crater detection pytorch models

Outputs of yolov5 tasks can be found in yolov5/runs/... depedning the tasks
Outputs of yolov8 and yolov12 tasks can be found in ultralytics1/runs/... depedning the tasks
