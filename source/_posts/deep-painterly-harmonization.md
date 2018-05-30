---
layout: post
title:  "深度绘画协调 Deep Painterly Harmonization"
description: P图应该是每个会ps的同学都玩过，要做到以假乱真还是需要强大的ps功底，现在通过深度学习可以做到以假乱真，傻傻分不清楚。
cover_image: images/TB1crXoubGYBuNjy0FoXXciBFXa-3540-520.jpg
categories:
  - Blog
tag:
  - AI
  - Paper
date: 2018/05/29 11:29:16
---

P图应该是每个会ps的同学都玩过，要做到以假乱真还是需要强大的ps功底，现在通过深度学习可以做到以假乱真，傻傻分不清楚。如下图:

<p align='center'><img src='/images/DeepPainterlyHarmonization/data/11_target.jpg' style="width:32% !important"/><img src='/images/DeepPainterlyHarmonization/data/11_naive.jpg' style="width:32% !important"/><img src='/images/DeepPainterlyHarmonization/results/11_final_res2.png' style="width:32% !important"/></p>




### 看看新算法的不同


![](https://img.alicdn.com/tfs/TB1h22fuXOWBuNjy0FiXXXFxVXa-2870-1210.jpg)

风格化迁移算法目前有很多，但是在Cornell大学和Adobe的同学们看来，现存的算法比较弱。
要像上图这样，把美队的盾牌融合到意大利画家[Onofrio Bramante](https://it.wikipedia.org/wiki/Onofrio_Bramante)的作品里就比较困难，在这个作品中一些微小的差异就会让人感觉很明显。
全局风格迁移的效果表现类似图3（从左往右第3列图) ，无论是边界线、匹配色彩还是细化质地，都很难让粘贴部分拥有画作的原始风格。

于是他们搭建局部风格化的神经网络。

他们主要以Gatys团队发表的风格迁移[Image Style Transfer](https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf)技术为基础，用VGG搭建了一个two-pass算法，还额外引入了一些风格重建损失 (Reconstruction Losses) 来优化结果。

以下为各个算法效果对比:
![](https://img.alicdn.com/tfs/TB1vmY5ueuSBuNjy1XcXXcYjFXa-2342-1768.jpg)

作者还有能实现像素级别的风格迁移的成果[“Deep Photo Style Transfer”](https://arxiv.org/pdf/1703.07511.pdf)


### 最终成果

<escape>
  <p align='center'>
    <img src='/images/DeepPainterlyHarmonization/data/0_target.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/data/0_naive.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/results/0_final_res2.png' style="width:32% !important"/>
  </p>
  <p align='center'>
    <img src='/images/DeepPainterlyHarmonization/data/1_target.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/data/1_naive.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/results/1_final_res2.png' style="width:32% !important"/>
  </p>
  <p align='center'>
    <img src='/images/DeepPainterlyHarmonization/data/2_target.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/data/2_naive.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/results/2_final_res2.png' style="width:32% !important"/>
  </p>
  <p align='center'>
    <img src='/images/DeepPainterlyHarmonization/data/3_target.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/data/3_naive.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/results/3_final_res2.png' style="width:32% !important"/>
  </p>
  <p align='center'>
    <img src='/images/DeepPainterlyHarmonization/data/5_target.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/data/5_naive.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/results/5_final_res2.png' style="width:32% !important"/>
  </p>
  <p align='center'>
    <img src='/images/DeepPainterlyHarmonization/data/6_target.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/data/6_naive.jpg' style="width:32% !important"/>
    <img src='/images/DeepPainterlyHarmonization/results/6_final_res2.png' style="width:32% !important"/>
  </p>
</escape>

### 参考资料
- Github: [deep-painterly-harmonization][1]
- 论文地址: [https://arxiv.org/abs/1804.03189][2]
- [Image Style Transfer][3]
- [画家 Onofrio Bramante][4]
- [Deep Photo Style Transfer][5]

[1]: https://github.com/luanfujun/deep-painterly-harmonization
[2]: https://arxiv.org/abs/1804.03189
[3]: https://www.cv-foundation.org/openaccess/content_cvpr_2016/papers/Gatys_Image_Style_Transfer_CVPR_2016_paper.pdf
[4]: https://it.wikipedia.org/wiki/Onofrio_Bramante
[5]: https://arxiv.org/pdf/1703.07511.pdf