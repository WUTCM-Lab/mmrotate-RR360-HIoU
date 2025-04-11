# Bow Direction Detection Based on Angular Coding with Heading Intersection over Union Loss

## 简介

这是 [Bow Direction Detection Based on Angular Coding with Heading Intersection over Union Loss](https://ieeexplore.ieee.org/document/10946139)
论文的代码实现

> 准确的船首方向检测对于船舶轨迹预测和港口监控至关重要。现有的船舶检测网络通常输出 180 度范围内的角度，而扩展到 360
> 度会引入周期性问题，影响旋转交集比率（Rotation Intersection over Union, RIoU）的准确性。本文提出了一种新的船首方向检测算法，扩展了网络输出至
> 360 度，并集成了航向交集比率损失（Heading Intersection over Union Loss, HIoU），以提高检测的准确性和鲁棒性。此外，还设计了一个
> HIoU 损失函数，旨在改善船首方向识别并减少哈希码中的量化误差。该算法在三个数据集上进行了评估：FGSD、OHD-SJTU-S 和
> OHD-SJTU-L。在 FGSD 数据集上，算法实现了 91.14% 的平均精度（mAP）。在 OHD-SJTU-S 数据集上，达到 63.3% 的 mAP50:95 和 90.7%
> 的船首方向预测准确率。在OHD-SJTU-L数据集上，mAP50:95 为 29.2%，准确率为 80.2%。

## 环境配置

```shell
# 假设已经安装mmengine、mmcv 2.x、mmdetection
git clone https://github.com/open-mmlab/mmrotate -b dev-1.x
cd mmrotate
export MMROTATE_HOME=$(pwd)
pip install -v -e .
```

## 快速开始

训练

```shell
cd $MMROTATE_HOME
python projects/HIoU/tools/train.py \
    projects/HIoU/configs/hiou/rotated_rtmdet_l_l1_pscrn3_tsiou_csta2b0.2-3x-fgsd.py \
    --d
```

测试自行训练的权重

```shell
cd $MMROTATE_HOME
python projects/HIoU/tools/test.py \
    projects/HIoU/configs/hiou/rotated_rtmdet_l_l1_pscrn3_tsiou_csta2b0.2-3x-fgsd.py \
    path/to/epoch_xx.pth
```

## Citation

```bibtex
@ARTICLE{10946139,
  author={Chen, Yaxiong and Liu, Jiang and Huang, Qiangqiang and Sun, Hao and Xiong, Shengwu and Lu, Xiaoqiang},
  journal={IEEE Transactions on Geoscience and Remote Sensing}, 
  title={Bow Direction Detection Based on Angular Coding with Heading Intersection over Union Loss}, 
  year={2025},
  volume={},
  number={},
  pages={1-1},
  keywords={Accuracy;Object detection;Marine vehicles;Prediction algorithms;Encoding;Technological innovation;Optimization;Training;Artificial intelligence;Shape;360-Degree Angle Processing;Angle Encoding;Bow Direction Detection;Computer Vision},
  doi={10.1109/TGRS.2025.3556480}}
```
