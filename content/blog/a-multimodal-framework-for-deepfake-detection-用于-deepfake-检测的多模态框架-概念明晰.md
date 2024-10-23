---
title: A Multimodal Framework for DeepFake Detection 用于 DeepFake 检测的多模态框架 概念明晰
date: 2024-10-23T12:45:07.772Z
---

梅尔频谱图（Mel Spectrogram）是一种将音频信号转换为视觉表示的方法.是一种视觉表示，用于展示信号在频率和时间上的变化情况。它通过将信号分解为不同频率成分并显示这些频率成分在整个信号中的变化来工作。
单峰数据集：具有一个、两个、三个众数的数据集合，分别称为单峰的（unimodal）、双峰的（bimodal）、三峰的（trimodal）数据集。
多模态框架由视频监测和音频检测两个部分组成：
音频部分：输入视频将首先提取其音频并通过音频深度伪造检测模型——模型生成并提取音频样本的完美梅尔频谱图以及相同的 MFCC——归类为真实or深度伪造音频
音频模型部分同时对比了Random Forest、Gradient Boosting 、CNN等，综合精度、召回率、F1 分数和准确性等指标看来，VGG19效果最好。
![屏幕截图 2024-10-23 202227.png](https://github.com/FengYangGuang/tinymind-blog/blob/main/assets/images/2024-10-23/1729686160368.png?raw=true)
视频部分：数据预处理部分，首先利用Haar Cascade提取9个视频特征[特征提取]——送入人工神经网络ANN训练[人工神经网络的前馈结构使它们能够跨多个层处理输入数据，捕获简单模型中缺少的非线性关系和高度抽象。]——归类为真实or深度伪造视频
视频模型训练部分同时对比了Decision Tree 决策树、Random Forest 随机森林、Bagging 和XGBoost，综合精度、召回率、F1 分数和准确性等指标看来ANN效果最好。