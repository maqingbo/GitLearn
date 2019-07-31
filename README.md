## 参考

- [《玩转 Git 三剑客》](https://time.geekbang.org/course/intro/145?code=o9e8mlOfOwtb-R97tPjzT2oifElj8ToMC7H2CDYtWOQ%3D&amp%3Bamp%3Butm_term=SPoster)
- [《Pro Git》](https://git-scm.com/book/zh/v2)

笔记只记录了我自己对于 Git 不了解或者不熟悉的地方，并不会每一个部分都详细讲解，所以它可能不完全适合你。

## 课程综述

### 版本管理的演变

`版本管理系统`英文缩写 —— VCS

- VCS 出现前
	- ⽤⽬录拷⻉区别不同版本
	- 公共⽂件容易被覆盖
	- 成员沟通成本很⾼，代码集成效率低下
- 集中式 VCS（CVS、SVN）
	- 有集中的版本管理服务器
	- 具备⽂件版本管理和分⽀管理能⼒
	- 集成效率有明显地提⾼
	- 客户端必须时刻和服务器相连
- 分布式 VCS（Git）
	- 服务端和客户端都有完整的版本库
	- 脱离服务端，客户端照样可以管理版本
	- 查看历史和版本⽐较等多数操作，都不需要访问服务器，⽐集中式 VCS 更能提⾼版
	- 本管理效率
- Git 特点
	- 最优的存储能⼒
	- ⾮凡的性能
	- 开源的
	- 很容易做备份
	- ⽀持离线操作
	- 很容易定制⼯作流程

### 课程内容

- Git
	- 工作原理
	- 如何使用
- GitHub
	- 全球最大开源社区
	- GitHub 生态
- GitLab
	- 一般的公司会基于 GitLab 做自己平台的二次开发


## 初次运行 Git 前的配置

安装完 Git 应该做的第一件事就是设置你的`用户名`与`邮件地址`。 这样做很重要，因为每一个 Git 的提交都会使用这些信息，并且它会写入到你的每一次提交中，不可更改：

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

`config` 的三个作用域：

```
// 只对仓库有效（权限最高）
$ git config --local

// 对目前登录用户所有仓库有效（权限次之，默认就是 local）
$ git config --global

// 对系统所有用户有效（权限最低）
$ git config --system
```

查看设置：

```
$ git config --list --local
```

清除设置：

```
$ git config --unset --local user.name
```

### 给文件重命名的简便方法

常用方法：

在`工作区`重命名文件，此时执行`git status`会提示添加新文件和删除旧文件。然后我们添加新文件到`暂存区`，并删除旧文件，步骤繁琐，并且重命名的过程并不直观。

简便方法：

```
git mv 旧名称 新名称
```

直接在暂存区修改，一步到位！

### `.git`目录、commit、tree 和 blob

:::tip
这几节课程作者开始讲解关于 Git 原理的东西，但是讲的很没有章法。想更好的理解这一部分的知识点，可以参考《Pro Git》的`Git 内部原理`这一章。
:::

下面对于 Git 的原理进行基本梳理：

首先要弄明白一点，从根本上来讲 Git 是一个内容寻址
（content-addressable）文件系统，并在此之上提供了一个版本控制系统的用户界面。

Git 进行版本管理的信息全部存放于`.git`文件夹。

```
$ ls .git

branches/
config
description
HEAD
hooks/
info/
objects/
refs/
```


未完待续...
