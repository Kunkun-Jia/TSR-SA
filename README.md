# [A real-time and high-precision method for small traffic-signs recognition](https://link.springer.com/article/10.1007/s00521-021-06526-1)
This repo contains the official implementation(Based on [Darknet](https://github.com/AlexeyAB/darknet)) of TSR-SA: A real-time and high-precision method for small traffic-signs recognition.

![TSR-SA](https://github.com/Kunkun-Jia/TSR-SA/blob/main/pics/TSR-SA.png)

[**Paper**](https://link.springer.com/article/10.1007/s00521-021-06526-1) | [**Code**](https://github.com/Kunkun-Jia/TSR-SA)
# Dataset
We use [TT100K(Tsinghua-Tencent 100K)](http://cg.cs.tsinghua.edu.cn/traffic-sign/) as dataset, and you need to convert the label format to YOLO format. For example:

1. Create the following folders in the root directory to store the datasets:
```
TSR-SA
└── VOC2007
    ├── Annotations
    ├── ImageSets
    │   └── Main
    ├── JPEGImages
    └── labels
```
2. Use `genfiles.py` to generate training and test sets:
```
TSR-SA
|── VOC2007
|   ├── Annotations
|   ├── ImageSets
|   │   └── Main
|   ├── JPEGImages
|   └── labels
├── 2007_test.txt
└── 2007_train.txt
```

# Install
More details about install in [Darknet](https://github.com/AlexeyAB/darknet#how-to-compile-on-linuxmacos-using-cmake).

# Training

### Mode
- YOLOv4 baseline of TT100K: `cfg/yolov4-tt100k_base`
- Introduce low-level features + increase detection fine-grained: `cfg/yolov4-tt100k-neck_head` 
- RFB-cross: `cfg/yolov4-tt100k-neck_head_rfb-c`

### Pre-training
- Download the pre-trained weights file under TSR-SA: [yolov4.conv.137](https://github.com/AlexeyAB/darknet/releases/download/darknet_yolo_v3_optimal/yolov4.conv.137)

### Fine-tuning on TT100K

Depending on the mode you want, choose the corresponding cfg file and use the following command to train:
- To train on Linux use command: 

`./darknet detector train cfg/tt100k.data cfg/yolov4-tt100k.cfg yolov4.conv.137`

- For training on Linux with mAP:

`./darknet detector train cfg/tt100k.data cfg/yolov4-tt100k.cfg yolov4.conv.137 -map`

### More command line usage about training
[How to train with multi gpu](https://github.com/AlexeyAB/darknet#how-to-train-with-multi-gpu)

# Testing
### For image 
`./darknet detector test cfg/tt100k.data cfg/yolov4-tt100k.cfg backup/yolov4-tt100k_base.weights -ext_output test.jpg`

### For video 

`./darknet detector test cfg/tt100k.data cfg/yolov4-tt100k.cfg backup/yolov4-tt100k_base.weights -ext_output test.mp4`

### More command line usage about testing
[How to use on the command line](https://github.com/AlexeyAB/darknet#how-to-use-on-the-command-line)

# Citation
```
@article{chen2022real,
  title={A real-time and high-precision method for small traffic-signs recognition},
  author={Chen, Junzhou and Jia, Kunkun and Chen, Wenquan and Lv, Zhihan and Zhang, Ronghui},
  journal={Neural Computing and Applications},
  volume={34},
  number={3},
  pages={2233--2245},
  year={2022},
  publisher={Springer}
}
```
