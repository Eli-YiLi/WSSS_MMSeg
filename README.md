# Weakly-supervised Semantic Segmentation part

### Introduction

This is a PyTorch implementation of [Pseudo-mask Matters in Weakly-supervised Semantic Segmentation](https://arxiv.org/pdf/2108.12995.pdf).(ICCV2021).

In this paper, we propose Coefficient of Variation Smoothing and Proportional Pseudo-mask Generation to generate high quality pseudo-mask in classification part.
In segmentation part, we propose Pretended Under-Fitting strategy and Cyclic Pseudo-mask for better utilization of pseudo-mask.

#### Data Preparation
1. Download VOC12 [OneDrive](https://1drv.ms/u/s!Agn5nXKXMkK5aigB0g238YxuTxs?e=FjGaBI), [BaiduYun](https://pan.baidu.com/s/1GL3zXZuapuXmH9E7Xy8-Fg)
2. Download COCO14 [BaiduYun](https://pan.baidu.com/s/1GL3zXZuapuXmH9E7Xy8-Fg)
3. Download pretrained models [OneDrive](https://1drv.ms/u/s!Agn5nXKXMkK5aigB0g238YxuTxs?e=FjGaBI), [BaiduYun](https://pan.baidu.com/s/1GL3zXZuapuXmH9E7Xy8-Fg)
(extract code of BaiduYun: mtci)

#### Get Started
    (data preparation)
    git clone https://github.com/Eli-YiLi/WSSS_MMSeg.git
    cd WSSS_MMSeg
    mkdir data
    cd data
    ln -s [path to model files] models
    ln -s [path to VOC12] voc12
    ln -s [path to COCO14] coco2014
    ln -s [path to your voc pseudo-mask] voc12/VOC2012/ppmg
    ln -s [path to your coco pseudo-mask] coco2014/voc_format/ppmg

    (install mmsegmentation and mmcv(our version is 1.1.4) as MMSegmentation part)

    (train and val, slurm)
    bash tools/run_wsss.sh [Partition] [Dataset] [Architecture]
# MMSegmentation part

<div align="center">
  <img src="resources/mmseg-logo.png" width="600"/>
</div>
<br />

[![PyPI](https://img.shields.io/pypi/v/mmsegmentation)](https://pypi.org/project/mmsegmentation)
[![docs](https://img.shields.io/badge/docs-latest-blue)](https://mmsegmentation.readthedocs.io/en/latest/)
[![badge](https://github.com/open-mmlab/mmsegmentation/workflows/build/badge.svg)](https://github.com/open-mmlab/mmsegmentation/actions)
[![codecov](https://codecov.io/gh/open-mmlab/mmsegmentation/branch/master/graph/badge.svg)](https://codecov.io/gh/open-mmlab/mmsegmentation)
[![license](https://img.shields.io/github/license/open-mmlab/mmsegmentation.svg)](https://github.com/open-mmlab/mmsegmentation/blob/master/LICENSE)
[![issue resolution](https://isitmaintained.com/badge/resolution/open-mmlab/mmsegmentation.svg)](https://github.com/open-mmlab/mmsegmentation/issues)
[![open issues](https://isitmaintained.com/badge/open/open-mmlab/mmsegmentation.svg)](https://github.com/open-mmlab/mmsegmentation/issues)

Documentation: https://mmsegmentation.readthedocs.io/

## Introduction

MMSegmentation is an open source semantic segmentation toolbox based on PyTorch.
It is a part of the OpenMMLab project.

The master branch works with **PyTorch 1.3 to 1.6**.

![demo image](resources/seg_demo.gif)

### Major features

- **Unified Benchmark**

  We provide a unified benchmark toolbox for various semantic segmentation methods.

- **Modular Design**

  We decompose the semantic segmentation framework into different components and one can easily construct a customized semantic segmentation framework by combining different modules.

- **Support of multiple methods out of box**

  The toolbox directly supports popular and contemporary semantic segmentation frameworks, *e.g.* PSPNet, DeepLabV3, PSANet, DeepLabV3+, etc.

- **High efficiency**

  The training speed is faster than or comparable to other codebases.

## License

This project is released under the [Apache 2.0 license](LICENSE).

## Changelog

v0.7.0 was released in 07/10/2020.
Please refer to [changelog.md](docs/changelog.md) for details and release history.

## Benchmark and model zoo

Results and models are available in the [model zoo](docs/model_zoo.md).

Supported backbones:

- [x] ResNet
- [x] ResNeXt
- [x] [HRNet](configs/hrnet/README.md)
- [x] [ResNeSt](configs/resnest/README.md)
- [x] [MobileNetV2](configs/mobilenet_v2/README.md)

Supported methods:

- [x] [FCN](configs/fcn)
- [x] [PSPNet](configs/pspnet)
- [x] [DeepLabV3](configs/deeplabv3)
- [x] [PSANet](configs/psanet)
- [x] [DeepLabV3+](configs/deeplabv3plus)
- [x] [UPerNet](configs/upernet)
- [x] [NonLocal Net](configs/nonlocal_net)
- [x] [EncNet](configs/encnet)
- [x] [CCNet](configs/ccnet)
- [x] [DANet](configs/danet)
- [x] [GCNet](configs/gcnet)
- [x] [ANN](configs/ann)
- [x] [OCRNet](configs/ocrnet)
- [x] [Fast-SCNN](configs/fastscnn)
- [x] [Semantic FPN](configs/sem_fpn)
- [x] [PointRend](configs/point_rend)
- [x] [EMANet](configs/emanet)
- [x] [DNLNet](configs/dnlnet)
- [x] [CGNet](configs/cgnet)
- [x] [Mixed Precision (FP16) Training](configs/fp16/README.md)

## Installation

Please refer to [INSTALL.md](docs/install.md) for installation and dataset preparation.

## Get Started

Please see [getting_started.md](docs/getting_started.md) for the basic usage of MMSegmentation.
There are also tutorials for [adding new dataset](docs/tutorials/new_dataset.md), [designing data pipeline](docs/tutorials/data_pipeline.md), and [adding new modules](docs/tutorials/new_modules.md).

A Colab tutorial is also provided. You may preview the notebook [here](demo/MMSegmentation_Tutorial.ipynb) or directly [run](https://colab.research.google.com/github/open-mmlab/mmsegmentation/blob/master/demo/MMSegmentation_Tutorial.ipynb) on Colab.

## Contributing

We appreciate all contributions to improve MMSegmentation. Please refer to [CONTRIBUTING.md](.github/CONTRIBUTING.md) for the contributing guideline.

## Acknowledgement

MMSegmentation is an open source project that welcome any contribution and feedback.
We wish that the toolbox and benchmark could serve the growing research
community by providing a flexible as well as standardized toolkit to reimplement existing methods
and develop their own new semantic segmentation methods.
