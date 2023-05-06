## 数据集地址
```
链接：https://pan.baidu.com/s/10KgKKU1yOoy0Iou9-KKlaw?pwd=v6ei 
提取码：v6ei
```

## Prerequisites
Only tested on
* Anaconda3
* Python 3.7.1
* PyTorch 1.0.1
* Shapely 1.6.4
* opencv-python 4.0.0.21
* lanms-nova 1.0.3

## Installation
### 1. Clone the repo

```
git clone https://github.com/SakuraRiven/EAST.git
cd EAST
```

### 2. Data & Pre-Trained Model
* Download Train and Test Data: [ICDAR 2015 Challenge 4](http://rrc.cvc.uab.es/?ch=4&com=downloads). Cut the data into four parts: train_img, train_gt, test_img, test_gt.

* Download pre-trained VGG16 from PyTorch: [VGG16](https://drive.google.com/open?id=1HgDuFGd2q77Z6DcUlDEfBZgxeJv4tald) and our trained EAST model: [EAST](https://drive.google.com/open?id=1AFABkJgr5VtxWnmBU3XcfLJvpZkC2TAg). Make a new folder ```pths``` and put the download pths into ```pths```
  
```
mkdir pths
mv east_vgg16.pth vgg16_bn-6c64b313.pth pths/
```

Here is an example:
```
.
├── EAST
│   ├── evaluate
│   └── pths
└── ICDAR_2015
    ├── test_gt
    ├── test_img
    ├── train_gt
    └── train_img
```
## Train
Modify the parameters in ```train.py``` and run:
```
python train.py
```
## Detect
Modify the parameters in ```detect.py``` and run:
```
python detect.py
```
## Evaluate
* The evaluation scripts are from [ICDAR Offline evaluation](http://rrc.cvc.uab.es/?ch=4&com=mymethods&task=1) and have been modified to run successfully with Python 3.7.1.
* Change the ```evaluate/gt.zip``` if you test on other datasets.
* Modify the parameters in ```eval.py``` and run:
```
python eval.py
```
