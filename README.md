# FE-DETR
A Fourier-Enhanced, Edge-Aware Framework for UAV-Based Remote Sensing Object Detection

## Introduction
This project develops an object detection solution with Fourier-Enhanced and Edge-Aware Framework specifically optimized for the Aerial images' characteristics. The following peacture shows the architecture of FE-DETR.
![image](https://github.com/user-attachments/assets/77a0c38f-8ac7-4019-bb09-a871d33129d0)




Our algorithm is primarily built upon the Ultralytics open-source toolbox compatible with PyTorch 1.13+.

The core model implementation is located in ultralytics/nn/extra_models/, while training/testing configuration files can be found in ultralytics/cfg/default.yaml.

## Results and Models
300-epoch pre-trained FE-DETR: [Download](https://pan.baidu.com/s/1lITtp3PB4eKk2pwhr1LDlw?pwd=2bdw)

VisDrone2019 Performance
![image](https://github.com/user-attachments/assets/43e158c7-e126-489e-86a6-a9b072bfde69)



## Installation
First create and activate a virtual environment:
```shell
conda create --name XXX python=3.8.16 -y
conda activate XXX
```
Install PyTorch and CUDA compatible with your system:
```shell
conda install pytorch==1.13.1 torchvision==0.14.1 cudatoolkit=11.7 -c pytorch
```
Install mmcv and mmengine using OpenMMLab's mim:
```shell
pip install -U openmim
mim install mmcv==2.1.0
mim install mmengine==0.9.0
```

When using an older GPU, you need to check the computing power of your GPU, and select the CUDA version and Pytorch version that meet the corresponding mmcv and mmengine requirements based on the computing power. At the same time, you should also pay attention to the correspondence between the CUDA version and the Pytorch version.

The corresponding query document link is as follows:

[GPU computing power query](https://developer.nvidia.com/cuda-gpus)

[The correspondence between GPU computing power and CUDA version](https://docs.nvidia.com/datacenter/tesla/drivers/index.html#cuda-arch-matrix)

Note: This project cannot use an older version of mmcv, and the mmcv version should be greater than 2.0. Different versions of the documentation can be selected in the black box in the lower left corner of the documentation provided by this link. Please carefully follow the above instructions to check your GPU version and install it.
                         
![](https://notes.sjtu.edu.cn/uploads/upload_54d6a53693eb5559ab993b7c7cc9cdd8.jpg)

Additional dependencies:
```shell
pip install timm==0.9.8
pip install thop
pip install efficientnet_pytorch==0.7.1
pip install einops grad-cam==1.4.8
pip install dill==0.3.6
pip install albumentations==1.3.1
pip install pytorch_wavelets==1.3.0
pip install tidecv PyWavelets -i https://pypi.tuna.tsinghua.edu.cn/simple
```

Finally install project requirements:
```shell
pip install -r requirements.txt
```


## Tutorials
Refer to the [Ultralytics Quick Start Guide](https://docs.ultralytics.com/quickstart/) for basic usage. Additional resources:

- [Fundamentals](https://docs.ultralytics.com/models/rtdetr/)

- [Configuration Files](https://docs.ultralytics.com/reference/cfg/__init__/)

- [Custom Datasets](https://docs.ultralytics.com/yolov5/tutorials/train_custom_data/)

- [Custom Models](https://github.com/ultralytics/ultralytics/blob/main/ultralytics/cfg/models/README.md)


## Data Preparation

For VisDrone dataset preparation, please refer to: [How to prepare your VisDrone dataset](https://docs.ultralytics.com/datasets/detect/visdrone/)。


## Testing Our Mode
Run inference using:
```shell
python val.py ${CONFIG_FILE} ${CHECKPOINT_FILE} [optional arguments]
python detect.py ${CONFIG_FILE} ${CHECKPOINT_FILE} [optional arguments]
```

## Training Our Model
Single GPU Training
```shell
python train.py ${CONFIG_FILE} ${PRE-TRAIN_FILE} [optional arguments]
```

## Acknowledgments
We extend our gratitude to the Ultralytics open-source toolbox for its significant contributions to this project. The integrated preprocessing, training, and validation modules have greatly enhanced our model development efficiency!

Ultralytics is a community-driven project with contributions from various institutions and individuals. We appreciate all contributors who have supported algorithm implementation and feature development, as well as users who provided valuable feedback!
