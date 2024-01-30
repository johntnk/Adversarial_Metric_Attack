# abc
配置环境：Python3.7、 ananconda3 pycharm
此次运行的数据集为：Market-1501-v15.09.15
网络为：resnext
运行代码来源:https://github.com/SongBaiHust/Adversarial_Metric_Attack

运行顺序：prepare.py（需要更改文件路径 downloadpath和savepath）     model.py   resnext.py  Gen_Adv。py
(后面的evaluate.py暂时还没有改，需要前面都代码出结果才能运行看）


原代码的文档
# Adversarial Metric Attack for Person Re-identification
By [Song Bai](http://songbai.site/), [Yingwei Li](http://yingwei.li/), [Yuyin Zhou](https://yuyinzhou.github.io/), [Qizhu Li](https://qizhuli.github.io/), [Philip H.S. Torr](http://www.robots.ox.ac.uk/~tvg/index.php).

### Introduction
This repository contains the code of the paper [Adversarial Metric Attack for Person Re-identification](https://arxiv.org/abs/1901.10650). It proposes adversarial metric attack, a parallel methodology to the existing adversarial classification attack. Adversarial metric attack can be used to attack metric-based systems like person re-identification and generate adversarial examples accordingly.

### Prerequisites
* Pytorch 0.4.1
* Numpy
* Python 2.7

### How to Run

**Attack**. For example, attack a ResNet-50 model trained with cross-entropy loss

```Shell
python Gen_Adv.py \
 --loss_type=soft \
 --name=resnet_50 \
 --save_img \
 --save_fea
```
It will save the adversarial images and features.

**Test**.

```Shell
python evaluate_adv.py \
 --loss_type=soft \
 --name=resnet_50
```
Shell in one trial. We support three attacking methods, including FGSM, I-FGSM and MI-FGSM.

```bash
sh adv.sh
```
### Visualizations

#### Visualizations of Adversarial Examples

<p align="left"><img src="Images/1.png" width="176"> <img src="Images/2.png" width="176"> <img src="Images/3.png" width="176"> <img src="Images/4.png" width="176"></p>

#### Visualizations of Ranking List
<p align="left">
<img src="Images/untarget_illustration-crop-1.png" alt="Non-targeted Attack" width="720px">
</p>

The ranking list of non-targeted attack.

<p align="left">
<img src="Images/target_illustration_cropped-1.png" alt="Targeted Attack" width="720px">
</p>

The ranking list of targeted attack.

### Citation and Contact

If you find the code useful, please cite the following paper

    @article{bai2019adversarial,
      title={Adversarial Metric Attack for Person Re-identification},
      author={Bai, Song and Li, Yingwei and Zhou, Yuyin and Li, Qizhu and Torr, Philip HS},
      journal={arXiv preprint arXiv:1901.10650},
      year={2019}
    }

If you encounter any problems or have any inquiries, please contact songbai.site@gmail.com or songbai@robots.ox.ac.uk






