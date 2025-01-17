---
title: "4.2. 准备训练资料"
weight: 2
---


# 1. 取得高品质图片

训练用的图片最少最少要准备10张。重质不重量。因为我要训练的是单一人物且风格固定，图片不宜有复杂背景以及其他无关人物。

网路图片一张一张右键下载当然可以，不过要大量下载图片的话我会使用[Imgrd Grabber](https://ivonblog.com/posts/imgbrd-grabber-usage/)或[Hydrus Network](https://ivonblog.com/posts/setup-hydrus-network/)。

这里我准备了33张Hara绘制的斯卡萨哈

![](../../../images/bqSn4Xp.avif)


# 2. 裁切图片

下载图片后，要将训练图片裁切成512x512像素。你可以选择用SD WebUI自动裁切，或是手动裁切。


## 2.1. 自动裁切

裁切图片不会用到显卡计算。

1. 将要裁切的图片放到同一个目录下，例如`/home/ivon/桌面/input`。

2. 开启SD WebUI，进到Train → Preprocess images页面

![](../../../images/Screenshot_20230421_002313.webp)

3. 第一个栏位`Source directory`填写原始图片的路径

4. 第二个栏位`Destination directory`填写输出路径，例如`/home/ivon/桌面/cropped`

5. Width和Height设定为512x512

5. 点选Preprocess ，图片即会自动裁切。在那之后原始图片就可以删除，只留下裁切后的图片。


## 2.2. 手动裁切

手动把图片转成512x512理由是避免重要的部分被裁掉。

1. 安装修图软件[GIMP](https://www.gimp.org/)，点选档案→新增512x512像素的专案

![](../../../images/C2ScvyP.avif)

2. 点油漆桶将其漆成白色

![](../../../images/DsUDEu9.avif)

3. 将图片拖曳进画面，成为新的图层

![](../../../images/cLqIlXa.avif)

4. 点选工具→变形工具→缩放，缩放图片使其符合目前画布大小，再按Enter。

![](../../../images/TAoINha.avif)

5. 点选档案→Export，汇出成png。

![](../../../images/Lx95khX.avif)

6. 为加快后面图片的处理速度，按右下角删除目前图层，再拖新的图片进来，重复操作。

![](../../../images/fZ3D4Vb.avif)

7. 将33张Hara绘制的斯卡萨哈裁切后，统一放到名为`raw`的目录。

![](../../../images/O5Tpz0f.avif)


# 3. 预先给图片上提示词

接着要给图片预先上提示词，这样AI才知道要学习哪些提示词。

1. 启动SD WebUI，进入Train页面。

2. 进入Preprocess页面，`Source`输入裁切图片的路径，`Destination`填处理后图片输出的路径。

![](../../../images/YB1dJqc.avif)

3. 接着勾选`Create Flipped Copies`，建立翻转图片提升训练数量。

然后用Stable Diffusion训练真实图片的勾选`Use BLIP for caption`；训练动漫人物改勾选`Use DeepBooru for caption`。

4. 点选Preprocess，约几分钟后便会处理完成。输出的目录里面会含有每张图片对应的提示词txt文件。

![](../../../images/wNTq9uV.avif)

5. 点选开启txt文件，将你觉得无关的特征都删除，例如`2girls`这类太笼统的提示词。

6. 至此训练资料准备完成。
