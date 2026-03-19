# frp

[![Build Status](https://circleci.com/gh/fatedier/frp.svg?style=shield)](https://circleci.com/gh/fatedier/frp)
[![GitHub release](https://img.shields.io/github/tag/fatedier/frp.svg?label=release)](https://github.com/fatedier/frp/releases)
[![Go Report Card](https://goreportcard.com/badge/github.com/fatedier/frp)](https://goreportcard.com/report/github.com/fatedier/frp)
[![GitHub Releases Stats](https://img.shields.io/github/downloads/fatedier/frp/total.svg?logo=github)](https://somsubhra.github.io/github-release-stats/?username=fatedier&repository=frp)

- 原项目地址
  - 官网 https://gofrp.org/zh-cn/
  - GitHub仓库 https://github.com/fatedier/frp
- 我汉化和构建docker镜像的仓库
  - GitHub仓库 https://github.com/Firfr/frp_zh
  - Gitee仓库 https://gitee.com/firfe/frp_zh
  - DockerHub
    - 服务端 https://hub.docker.com/r/firfe/frps
    - 客户端 https://hub.docker.com/r/firfe/frpc

## 汉化&镜像制作

如果镜像拉取失败，请B站发私信，或提issues，  
华为云上的镜像仓库默认推送的镜像不是公开的，有可能是我忘记设置公开了。

当前制作镜像版本(或截止更新日期)：0.67.0

原项目没有中文，我就行了汉化，制作了中文docker镜像。并提供汉化的 Windows AMD64 版本的服务端和客户端。

只做了汉化和简单修改，有问题，请到原作者仓库处反馈。

欢迎关注我B站账号 [秦曱凧](https://space.bilibili.com/17547201) (读作 qín yuē zhēng)  

有需要帮忙部署这个项目的朋友,一杯奶茶,即可程远程帮你部署，需要可联系。  
微信号 `E-0_0-`  
闲鱼搜索用户 `明月人间`  
或者邮箱 `firfe163@163.com`  
如果这个项目有帮到你。欢迎start。也厚颜期待您的[打赏](https://gitee.com/firfe/me)。

### 镜像

从阿里云或华为云镜像仓库拉取镜像，注意填写镜像标签，镜像仓库中没有`latest`标签

#### 服务端

- 国内仓库
  - AMD64镜像
    ```bash
    swr.cn-north-4.myhuaweicloud.com/firfe/frps:0.67.0
    ```
  - ARM64镜像
    ```bash
    swr.cn-north-4.myhuaweicloud.com/firfe/frps:0.67.0-arm64
    ```
- DockerHub仓库
  - AMD64镜像
    ```bash
    firfe/frps:0.67.0
    ```
  - ARM64镜像
    ```bash
    firfe/frps:0.67.0-arm64
    ```

#### 客户端

- 国内仓库
  - AMD64镜像
    ```bash
    swr.cn-north-4.myhuaweicloud.com/firfe/frpc:0.67.0
    ```
  - ARM64镜像
    ```bash
    swr.cn-north-4.myhuaweicloud.com/firfe/frpc:0.67.0-arm64
    ```
- DockerHub仓库
  - AMD64镜像
    ```bash
    firfe/frpc:0.67.0
    ```
  - ARM64镜像
    ```bash
    firfe/frpc:0.67.0-arm64
    ```

### 部署

部署方式和原项目一样，参考原项目文档。

也可以参考[本地调试命令记录](本地调试命令记录.md)中**构建镜像本地调试**部分的部署方法。

### 效果截图

| ![服务端-概览](图片/服务端-概览.jpg) | ![服务端-连接客户端](图片/服务端-连接客户端.jpg) |
| :-: | :-: |
| ![服务端-客户端详情](图片/服务端-客户端详情.jpg) | ![服务端-转发详情](图片/服务端-转发详情.jpg) |
| ![服务端-代理](图片/服务端-代理.jpg) | ![服务端-连接流量](图片/服务端-连接流量.jpg) |
| ![客户端-概览](图片/客户端-概览.jpg) | ![客户端-配置](图片/客户端-配置.jpg) |
