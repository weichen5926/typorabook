# 胸部X线报告生成的变分主题推理

Variational Topic Inference for Chest X-Ray Report Generation

论文：MICCIA2021  笔记：2022.7.19

## 问题

由于具有不同专业知识和经验的不同放射科医生编写的报告中固有的多样性和不确定性，从医学数据中学习具有挑战性。

## 提出方法

提出了用于自动生成报告的变分主题推理。具体来说，我们引入了一组主题作为潜在变量，通过在潜在空间中对齐图像和语言模式来指导句子生成。主题在条件变分推理框架中推断，每个主题都控制报告中句子的生成。

## 模型结构

![image-20220719150129907](../image/image-20220719150129907.png)

### 变分主题推理（VTI）

引入了一组潜在变量，每个变量定义为控制句子生成的主题。该模型通过最大化证据下限目标（ELBO）进行优化。

使用了变分推理的知识推到公式。后面补充

现在理解就是利用标签report送入编码训练生成一个中间状态量e[SENT],这个状态量类似bert里，单纯用来聚合report的信息的，利用ELBO使得视觉状态与e[SENT]状态最小，起到对齐效果。

e[SENT]的训练用到VAE的知识，后面补充