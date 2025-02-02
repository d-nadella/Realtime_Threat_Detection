# How to Train YOLOv5 on Custom Objects

## Before you start
Let's make sure that we have access to GPU and Install YOLOv5 using below code in <a href="https://colab.research.google.com/github/ultralytics/yolov5/blob/master/classify/tutorial.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

```bash
!git clone https://github.com/ultralytics/yolov5  # clone
%cd yolov5
%pip install -qr requirements.txt comet_ml  # install

import torch
import utils
display = utils.notebook_init()  # checks
```

## Preparing a custom dataset
- Prepare a custom dataset by collecting images, label them, and export them in the proper YOLO format as provided in train_data folder using [MakeSense AI](https://www.makesense.ai/) 
- Each text file starts with a list of objects from its corresponding image and concludes with the object's coordinates. This dataset serves as the foundation for our training.

## Train Custom YOLOv5 Detector
Prepare custom_data.yaml file pointing it to our train_data folder Train and Val images path. Adjust batch and epochs for increasing accuracy percentage for your dataasets if required.

```bash
!python train.py --img 640 --batch 16 --epochs 200 --data custom_data.yaml --weights yolov5s.pt --cache
```

```bash
200 epochs completed in 0.068 hours.
Optimizer stripped from runs/train/exp8/weights/last.pt, 14.4MB
Optimizer stripped from runs/train/exp8/weights/best.pt, 14.4MB

Validating runs/train/exp8/weights/best.pt...
Fusing layers... 
Model summary: 157 layers, 7012822 parameters, 0 gradients, 15.8 GFLOPs
                 Class     Images  Instances          P          R      mAP50   mAP50-95: 100% 1/1 [00:00<00:00,  4.96it/s]
                   all         11         22      0.779      0.864      0.837      0.428
Results saved to runs/train/exp8
```

## Execution to evaluate Custom YOLOv5 Detector Performance
Adjust weights file to your generated file from above step and play with Confidence argument for accurate detection.
```bash
!python detect.py --weights runs/train/exp8/weights/last.pt --img 640 --conf 0.35 --source ../DetectFromVideo1.mp4
```
