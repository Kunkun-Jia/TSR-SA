# [A real-time and high-precision method for small traffic-signs recognition](https://link.springer.com/article/10.1007/s00521-021-06526-1)
This repo contains the official implementation of TSR-SA: A real-time and high-precision method for small traffic-signs recognition.
# Dataset
We use [TT100K(Tsinghua-Tencent 100K)](http://cg.cs.tsinghua.edu.cn/traffic-sign/), and you need to convert the label format to YOLO format.

Then create the following folders in the root directory to store the datasets:
```
TSR-SA
└── VOC2007
    ├── Annotations
    ├── ImageSets
    │   └── Main
    ├── JPEGImages
    └── labels
```

# Install
More details about install in [Darknet](https://github.com/AlexeyAB/darknet#how-to-compile-on-linuxmacos-using-cmake).
# Training

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
