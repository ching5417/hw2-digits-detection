# hw2-digits-detection
Code for NCTU Selected Topics in Visual Recognition using Deep Learning Homework 2

## Hardware
The following specs were used to create the original solution.
- Ubuntu 20.04 LTS
- Intel(R) Core(TM) i7-6700 CPU @ 3.40GHz (8 Cores)
- 1x NVIDIA GeForce GTX 1080

## Reproducing Submission
To reproduct the training and testing process, do the following steps:
1. [Installation](#installation)
2. [Training](#training)
6. [Make Submission](#make-submission)

## Installation
All requirements should be detailed in requirements.txt. Using Anaconda is strongly recommended.
```
pip install -r requirements.txt
```

## Dataset Preparation
All required files are already in data directory.

## Training

### Train models
To train models, run following commands.
```
$ cd yolov5/
$ python train.py \
  [--img] \
  [--batch] \
  [--epochs] \
  [--data] \
  [--weights] \
  [--device]
```
After training, the model will save to `/yolov5/runs/train/exp/weights/` folder.
```
model
+- best.pt
+- last.pt 
```
[Here](https://drive.google.com/drive/folders/19NdivEm3QpWdGyAFCNiH1GPpfkvJo2r2?usp=sharing) download the model (ex: `exp11/best.pt`)

## Make Submission
Following command will ensemble of all models and make submissions.
```
$ python test.py \
  --source {testfolder} \
  --weights {modelsavepath} \
  --device 0,1,... \
  --conf 0.25 \
  --save-txt \
  --save-conf
```
After testing, it will output a `0856174.json` in `yolov5/runs/detect/exp/json/` folder.

I also put my testing result in `output/` folder.
