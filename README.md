# Partial-Order-Pruning

Partial Order Pruning: for  Best Speed/Accuracy Trade-off in Neural Architecture Search, CVPR 2019

****

## Abstract
Achieving good speed and accuracy trade-off on target platform is very important in deploying deep neural networks. Most existing automatic architecture search approaches only pursue high performance but ignores such an important factor. In this work, we propose an algorithm "Partial Order Pruning" to prune architecture search space with partial order assumption, quickly lift the boundary of speed/accuracy trade-off on target platform, and automatically search the architecture with the best speed and accuracy trade-off. Our algorithm explicitly take profile information about the inference speed on target platform into consideration. With the proposed algorithm, we present several "Dongfeng(东风)" networks that provide high accuracy and fast inference speed on various application GPU platforms. By further searching decoder architecture, our DF-Seg real-time segmentation models yields state-of-the-art speed/accuracy trade-off on both embedded device and high-end GPU.

***

## Experiments

1.We conduct backbone architecture searching experiments on TX2:

| 	模型(Model)		|	ImageNet Val. Top-1 Acc.	| Latency(ms)/224x224|
| :---------------- |:-----------------------------:|:------------------:|
| 	东风一(DF1)		|			69.78%				|        2.5         |
| 	东风二(DF2)		|			73.92%				|        5.0         |
| 	东风二甲(DF2A)	|			76.00%				|        6.5         |


2.With our Dongfeng backbone network (searched on TX2), we conduct decoder architecture search experiments on both TX2 and 1080Ti:

|     Model     | Cityscapes mIoU (Val/Test) | FPS(TX2/TensorRT-3.0.4) |FPS(1080Ti/TensorRT-3.0.4)|FPS(1080Ti/TensorRT-3.0.4)| FPS(Titan X/Caffe) |
| :------------ |:--------------------------:|:----------:|:-----------:|:-----------:|:------------------:|
| Resolution    |        1024x2048           |  640x384   |  1024x2048  |  1024x1024  |      1024x2048     |
| DFlite-Seg-d8 |        71.7/-              |     -      |    157.4    |    263.4    |        45.7        |
| DF1-Seg-d8    |        72.4/71.4           |    92.7    |    136.9    |    232.6    |        40.2        |
| DFlite-Seg    |        73.4/-              |     -      |    118.4    |    202.5    |        33.8        |
| DF1-Seg       |        74.1/73.0           |    71.4    |    106.1    |    182.1    |        30.7        | 
| DF2-Seg1      |        75.9/74.8           |    44.9    |    67.2     |      -      |        20.5        |
| DF2-Seg2      |        76.9/75.3           |    39.9    |    56.3     |      -      |        17.7        |


3.Dongfeng models are designed for GPU platforms. We further conduct backbone and decoder architecture searching experiments on Snapdragon 845 CPU platform:

|			 Model	       | Cityscapes mIoU (Val/Test) | FPS(Snapdragon 845) |
|:--------------------------------:|:--------------------------:|:------------------------:|
|        Resolution        |         1024x2048          |       640x384            |
|            PL1A-Seg              |         68.7/69.1          |        52.0              |


***

## Snapshots

欢迎使用“东风”系列模型，万事俱备，只欠东风！

df1.caffemodel
https://drive.google.com/open?id=1yA9DLSy3PEMQD3R92vKr6CEaOJ0NrOVm

df2.caffemodel
https://drive.google.com/open?id=1K0QPFD6XtKnMsrrOLSarnk3C1zmhZqpC

df2a.caffemodel
https://drive.google.com/open?id=1H5T-nz1D2DCLtma-alkR_CxGAHKewbql

df1seg.caffemodel
https://drive.google.com/open?id=1v-UCb1VIHGtIR9eXiPgdUu9wkDpemNTW

df1seg_mergebn.caffemodel
https://drive.google.com/open?id=17ZROC9dJAN8dxkpvTzHQRTS9soCwBOXJ

df2seg1.caffemodel
https://drive.google.com/open?id=1mCdozRO4BxDV-NS6secKuvaTNWEFcv_u

df2seg1_mergebn.caffemodel
https://drive.google.com/open?id=1RfdYtc7YzM5zYoANsRiB-XJMkvYfy_mv

df2seg2.caffemodel
https://drive.google.com/open?id=1D7bgq7h9OUQVY4LYA-x0B2FY8pnVgz3o

df2seg2_mergebn.caffemodel
https://drive.google.com/open?id=1FtqRSEN90ynTgMeGH3ee5DC8ubvSHZ3z

df-lite_seg_mergebn.caffemodel
https://drive.google.com/open?id=1se9wAkZFyNGYInjrhtXTMIZy39ucMaDu


## Citation

If Dongfeng networks are useful for your research, please consider citing:

	@inproceedings{li2019partial,
	author = {Xin Li,
		Yiming Zhou,
		Zheng Pan,
		Jiashi Feng},
	title = {Partial Order Pruning: for Best Speed/Accuracy Trade-off in Neural Architecture Search},
	booktitle = {Proceedings of IEEE Conference on Computer Vision and Pattern Recognition (CVPR)},
	year = {2019}
	}



## Questions

Please contact 'xin.li@uisee.com'

