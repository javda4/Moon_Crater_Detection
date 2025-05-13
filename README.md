# Moon_Crater_Detection
## YOLOv5, YOLOv8, and YOLOv12 Usage Guide

This repository provides instructions on how to use YOLOv5, YOLOv8, and YOLOv12 for object detection tasks, including training, validation, and inference. YOLOv12 follows the same usage pattern as YOLOv8, with the only difference being that model and task calls are directed to `v12` instead of `v8`.

### Table of Contents
- [Installation](#installation)
- [Training](#training)
- [Validation](#validation)
- [Inference](#inference)
- [Custom Datasets](#custom-datasets)
- [Model Variants](#model-variants)

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

