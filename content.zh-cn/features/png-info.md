---
title: "2.6. 查看提示词参数 PNG Info"
weight: 6
---

SD WebUI绘制的图片都是PNG文件，并会记载绘制图片所使用的模型、提示词等信息。

如果有人分享未修改过的SD WebUI图片，那么你只要把它下载下来，于此界面上传图片，即会显示该图片背后使用的提示词。

![](/posts/stable-diffusion-webui-manuals/images/FgnyaOB.webp)

不过有些模型会使用[LoRA](/posts/stable-diffusion-webui-manuals/zh-cn/features/extra-networks/)和其他的小模型，这点可从提示词有无`< >`来判断。因此有时候完全照抄提示词是不够的，缺少的东西要手动下载。