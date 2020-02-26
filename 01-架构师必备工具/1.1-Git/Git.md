# Git

## 0. 什么是Git？

[Git官方指南-中文](https://git-scm.com/book/zh/v2)

Git是免费且开源的分布式版本控制系统，旨在快速高效地处理从小型到大型项目的所有内容。最初由Linux之父林纳斯·托瓦兹创作，于2005年以GPL发布。最初目的是为更好地管理Linux内核开发而设计。

Git易于学习，体积小，具有闪电般的快速性能。它具有本地分支，便捷的暂存区域和多个工作流等功能，其性能优于Subversion，CVS，Perforce和ClearCase等SCM工具。

## 1. Git的工作原理

### 1.1 Git-基础

- 直接记录快照，而非比较差异

Git 和其它版本控制系统（包括 Subversion 和近似工具）的主要差别在于 Git 对待数据的方法。 概念上来区分，其它大部分系统以文件变更列表的方式存储信息。 这类系统（CVS、Subversion、Perforce、Bazaar 等等）将它们保存的信息看作是一组基本文件和每个文件随时间逐步累积的差异。

![存储每个文件与初始版本的差异。](https://git-scm.com/book/en/v2/images/deltas.png)

Git 不按照以上方式对待或保存数据。 反之，Git 更像是把数据看作是对小型文件系统的一组快照。 每次你提交更新，或在 Git 中保存项目状态时，它主要对当时的全部文件制作一个快照并保存这个快照的**索引**。 为了高效，如果文件没有修改，Git 不再重新存储该文件，而是只保留一个链接指向之前存储的文件。 Git 对待数据更像是一个**快照流**。

![Git 存储项目随时间改变的快照。](https://git-scm.com/book/en/v2/images/snapshots.png)

这是 Git 与几乎所有其它版本控制系统的重要区别。 因此 Git 重新考虑了以前每一代版本控制系统延续下来的诸多方面。 Git 更像是一个小型的文件系统，提供了许多以此为基础构建的超强工具，而不只是一个简单的 VCS。

- 近乎所有操作都是本地执行

在 Git 中的绝大多数操作都只需要访问本地文件和资源(服务器文件的一个快照)，一般不需要来自网络上其它计算机的信息。

- Git 保证完整性

Git 中所有数据在存储前都计算校验和，然后以校验和来引用。 这意味着不可能在 Git 不知情时更改任何文件内容或目录内容。

Git 用以计算校验和的机制叫做 SHA-1 散列（hash，哈希）。 这是一个由 40 个十六进制字符（0-9 和 a-f）组成的字符串，基于 Git 中文件的内容或目录结构计算出来。 SHA-1 哈希看起来是这样：

`24b9da6552252987aa493b52f8696cd6d3b00373`

Git 中使用这种哈希值的情况很多，你将经常看到这种哈希值。 实际上，Git 数据库中保存的信息都是以**文件内容**的哈希值来索引，而不是**文件名**。

- Git 一般只添加数据

你执行的 Git 操作，几乎只往 Git 数据库中增加数据。 很难让 Git 执行任何不可逆操作，或者让它以任何方式清除数据。 同别的 VCS 一样，未提交更新时有可能丢失或弄乱修改的内容；但是一旦你提交快照到 Git 中，就难以再丢失数据，特别是如果你定期的推送数据库到其它仓库的话。

- 三种状态
  - 已提交（committed）: 表示数据已经安全的保存在本地数据库中。
  - 已修改（modified）: 已修改表示修改了文件，但还没保存到数据库中。
  - 已暂存（staged）：表示对一个已修改文件的当前版本做了标记，使之包含在下次提交的快照中。

由此引入 Git 项目的三个工作区域的概念：Git 仓库、工作目录以及暂存区域。

![工作目录、暂存区域以及 Git 仓库。](https://git-scm.com/book/en/v2/images/areas.png)

**Git仓库**目录是 Git 用来保存项目的元数据和对象数据库的地方。 这是 Git 中最重要的部分，从其它计算机克隆仓库时，拷贝的就是这里的数据。

**工作目录**是对项目的某个版本独立提取出来的内容。 这些从 Git 仓库的压缩数据库中提取出来的文件，放在磁盘上供你使用或修改。

**暂存区域**是一个文件，保存了下次将提交的文件列表信息，一般在 Git 仓库目录中。 有时候也被称作“索引”，不过一般说法还是叫暂存区域。

基本的 Git 工作流程如下：

1. 在工作目录中修改文件。
2. 暂存文件，将文件的快照放入暂存区域。
3. 提交更新，找到暂存区域的文件，将快照永久性存储到 Git 仓库目录。

### 1.2 Git-分支

#### 1.2.1 分支简介

当使用 git commit 进行提交操作时，Git 会先计算每一个子目录（本例中只有项目根目录）的校验和，然后在 Git 仓库中这些校验和保存为树对象。 随后，Git 便会创建一个提交对象，它除了包含上面提到的那些信息外，还包含指向这个树对象（项目根目录）的指针。如此一来，Git 就可以在需要的时候重现此次保存的快照。

假设现在有一个工作目录，里面包含了三个将要被暂存和提交的文件。

现在，Git 仓库中有五个对象：三个**blob 对象**（保存着文件快照）、一个**树对象**（记录着目录结构和 blob 对象索引）以及一个**提交对象**（包含着指向前述树对象的指针和所有提交信息）。

![首次提交对象及其树结构。](https://git-scm.com/book/en/v2/images/commit-and-tree.png)

做些修改后再次提交，那么这次产生的提交对象会包含一个指向上次提交对象（父对象）的指针。

![提交对象及其父对象。](https://git-scm.com/book/en/v2/images/commits-and-parents.png)

Git 的分支，其实本质上仅仅是指向提交对象的可变指针。 Git 的默认分支名字是 master。 在多次提交操作之后，你其实已经有一个指向最后那个提交对象的 master 分支。 它会在每次的提交操作中自动向前移动。

![分支及其提交历史。](https://git-scm.com/book/en/v2/images/branch-and-history.png)

- 分支创建: 这会在当前所在的提交对象上创建一个指针。

```
$ git branch branch_name # 仅仅创建一个分支，但是不会自动切换到新分支上去
```



![两个指向相同提交历史的分支。](https://git-scm.com/book/en/v2/images/two-branches.png)

- 分支切换 ： `HEAD`指针由指向`master`变为指向`testing`

`$ git branch testing`

![HEAD 指向当前所在的分支。](https://git-scm.com/book/en/v2/images/head-to-testing.png)

再提交一次：

![HEAD 分支随着提交操作自动向前移动。](https://git-scm.com/book/en/v2/images/advance-testing.png)

`testing` 分支向前移动了，但是` master `分支却没有，它仍然指向运行 `git checkout` 时所指的对象。再切换回`master`

**在切换分支时，一定要注意你工作目录里的文件会被改变。 如果是切换到一个较旧的分支，你的工作目录会恢复到该分支最后一次提交时的样子。 如果 Git 不能干净利落地完成这个任务，它将禁止切换分支。**

![检出时 HEAD 随之移动。](https://git-scm.com/book/en/v2/images/checkout-master.png)

在此时的`master`分支再做修改时将会出现项目分叉，可以在不同分支间不断地来回切换和工作，并在时机成熟时将它们合并起来。

![项目分叉历史。](https://git-scm.com/book/en/v2/images/advance-master.png)

#### 1.2.2 分支创建与合并



## 2. Git常用命令

- 获取帮助

```
$ git help <verb>
$ git <verb> --help
$ man git-<verb>
```

- 初始化已有目录与添加文件

```
$ git init
$ git add README.md
```

- 克隆仓库

```
$ git clone [url]  
# 支持https:// 或者 git:// 或者 ssh:// 三种协议
# 如果想在clone的同时重新命名，只需在地址后加名字就可以
```

- 记录跟踪

工作目录下的每一个文件都不外乎这两种状态：已跟踪或未跟踪。 已跟踪的文件是指那些被纳入了版本控制的文件，在上一次快照中有它们的记录，在工作一段时间后，它们的状态可能是未修改，已修改或已放入暂存区。 工作目录中除已跟踪文件以外的所有其它文件都属于未跟踪文件，它们既不存在于上次快照的记录中，也没有被放入暂存区。 初次克隆某个仓库的时候，工作目录中的所有文件都属于已跟踪文件，并处于未修改状态。

![Git 下文件生命周期图。](https://git-scm.com/book/en/v2/images/lifecycle.png)

``` 
$ git add filename # 跟踪新文件
$ git status # 检查当前文件状态
$ git status [-s|--short]  # 简洁方式查看文件状态
$ git diff # 查看尚未暂存的文件更新了哪些部分
$ git diff [--cached|staged]# 查看已经暂存起来的变化
```

- 查看提交历史

```
$ git log --stat # 简略统计信息
$ git log --pretty=[oneline|short|full|fuller]
$ git log [--since|--until] # 按时间
```

- 提交与撤销

```
$ git commit -m "balabala" # 提交
$ git commit --amend # 将暂存区中的文件提交
$ git reset HEAD filename # 取消暂存的文件
```

- 远程仓库

```
$ git remote # 列出每一个远程服务器的简写
$ git remote -v # 显示需要读写远程仓库使用的 Git 保存的简写与其对应的 URL
$ git remote add <shortname> <url> # 添加远程仓库
$ git push [remote-name] # 推动到远程仓库
$ git remote show [remote-name] # 查看远程仓库
```



## 3. Git冲突的原因

## 4. 架构师职责：Git Flow规范团队Git使用教程

