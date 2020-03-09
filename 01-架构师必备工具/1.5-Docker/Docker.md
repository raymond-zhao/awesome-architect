# Docker

## 0 什么是Docker？

**Docker**是一个[开放源代码](https://zh.wikipedia.org/wiki/開放原始碼)软件项目，让应用程序部署在[软件货柜](https://zh.wikipedia.org/wiki/作業系統層虛擬化)下的工作可以自动化进行，借此在[Linux](https://zh.wikipedia.org/wiki/Linux)操作系统上，提供一个额外的软件[抽象层](https://zh.wikipedia.org/wiki/抽象層)，以及[操作系统层虚拟化](https://zh.wikipedia.org/wiki/作業系統層虛擬化)的自动管理机制[[1\]](https://zh.wikipedia.org/wiki/Docker#cite_note-SYS-CON_Media-1)。

Docker利用[Linux核心](https://zh.wikipedia.org/wiki/Linux核心)中的资源分离机制，例如[cgroups](https://zh.wikipedia.org/wiki/Cgroups)，以及Linux核心[名字空间](https://zh.wikipedia.org/w/index.php?title=Linux命名空間&action=edit&redlink=1)（namespaces），来创建独立的[容器](https://zh.wikipedia.org/wiki/作業系統層虛擬化)（containers）。这可以在单一Linux实体下运作，避免引导一个[虚拟机](https://zh.wikipedia.org/wiki/虛擬機器)造成的额外负担[[2\]](https://zh.wikipedia.org/wiki/Docker#cite_note-2)。Linux核心对名字空间的支持完全隔离了工作环境中应用程序的视野，包括行程树、[网络](https://zh.wikipedia.org/wiki/计算机网络)、用户ID与挂载文件系统，而核心的cgroup提供资源隔离，包括[CPU](https://zh.wikipedia.org/wiki/CPU)、[存储器](https://zh.wikipedia.org/wiki/電腦記憶體)、block I/O与网络。从0.9版本起，Dockers在使用抽象虚拟是经由[libvirt](https://zh.wikipedia.org/wiki/Libvirt)的[LXC](https://zh.wikipedia.org/wiki/LXC)与systemd - nspawn提供界面的基础上，开始包括libcontainer库做为以自己的方式开始直接使用由Linux核心提供的虚拟化的设施，

依据行业分析公司“451研究”：“Dockers是有能力打包应用程序及其虚拟容器，可以在任何Linux服务器上运行的依赖性工具，这有助于实现灵活性和便携性，应用程序在任何地方都可以运行，无论是[公用云](https://zh.wikipedia.org/wiki/公用雲)、[私有云](https://zh.wikipedia.org/wiki/私有雲)、单机等。” [[3\]](https://zh.wikipedia.org/wiki/Docker#cite_note-3)。

## 1 了解Docker的镜像、仓库、容器

## 2 Docker基础支持简介

## 3 Kubernates入门到进阶

## 4 基于Kubernetes治理微服务