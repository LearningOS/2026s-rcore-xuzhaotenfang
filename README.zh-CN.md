# rCore-Tutorial-Code

> 本文是 [README.md](README.md) 的中文版。两者内容如有出入，以英文原版为准。

## 领取春夏季作业仓库

1. 加入 [2026 春夏季训练营](https://opencamp.cn/os2edu/camp/2026spring)，并绑定自己的 GitHub 账号。
2. 点击[领取作业仓库](https://github.com/LearningOS/2026s-enroll/issues/new?template=rcore.yml)，提交申请并接受仓库邀请。
3. 在回复的作业仓库中，按照下方教程完成实验并 push，在 Actions 和训练营网站查看成绩。

已领取过本课程的学员继续使用原作业仓库。

## 代码

- [实验源代码（Source Code of labs）](https://github.com/LearningOS/rCore-Tutorial-Code)

## 文档

- 简明手册：[rCore-Tutorial-Guide](https://LearningOS.github.io/rCore-Tutorial-Guide/)

- 详细教材：[rCore-Tutorial-Book-v3](https://rcore-os.github.io/rCore-Tutorial-Book-v3/)

## rCore Tutorial Code 的 OS API 文档

- [第 1 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch1/os/index.html)
  与 [第 2 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch2/os/index.html)
- [第 3 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch3/os/index.html)
  与 [第 4 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch4/os/index.html)
- [第 5 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch5/os/index.html)
  与 [第 6 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch6/os/index.html)
- [第 7 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch7/os/index.html)
  与 [第 8 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch8/os/index.html)
- [第 9 章 OS API 文档](https://learningos.github.io/rCore-Tutorial-Code/ch9/os/index.html)

## 相关资源

- [学习资源（Learning Resource）](https://github.com/LearningOS/rust-based-os-comp2025/blob/main/relatedinfo.md)

## 环境配置

先按[实验环境配置](https://learningos.github.io/rCore-Tutorial-Guide/0setup-devel-env.html)准备好 Linux、Rust 和 QEMU，再克隆自己的作业仓库。各章节中的 `rust-toolchain.toml` 指定了课程使用的 Rust 版本。

```bash
$ git clone https://github.com/LearningOS/2026s-rcore-[YOUR_USER_NAME].git
$ cd 2026s-rcore-[YOUR_USER_NAME]
```

## 构建与运行

```bash
# 先配置好构建与运行环境
$ git clone https://github.com/LearningOS/rCore-Tutorial-Test.git user
$ git checkout ch$ID
$ cd os
# 在 ch$ID 中运行操作系统
$ make run
```

如果你想使用 Docker，请先切换到所需章节分支并回到作业仓库根目录，然后运行：

```bash
# 将 `rCore-Tutorial-Test` 仓库克隆到本机后，可用以下命令构建并运行：
$ cd ..
$ make build_docker
$ make docker
```

如果在 Docker 中访问 GitHub 等境外资源时遇到网络问题，可根据所处阶段参考以下建议：

- 拉取（docker pull）镜像：
  1. 使用代理：https://docs.docker.com/reference/cli/docker/image/pull/#proxy-configuration

  2. 使用可用的国内镜像源（请自行搜索）

- 构建（docker build）镜像：使用代理 https://docs.docker.com/engine/cli/proxy/#build-with-a-proxy-configuration

- 运行（docker run）容器：使用代理相关选项，操作方式与「构建镜像」类似，可自行参考相关资料

本仓库提供 `ch1` 至 `ch8`；请将 `$ID` 替换为对应章节的数字。第 9 章的 API 文档作为拓展阅读保留。

## 评测

在已配置好环境的作业仓库根目录中运行。首次需要下载检查器；若已有 `ci-user/` 目录则可直接复用，同时请保留自己的代码以及 `reports/` 中的实验报告。后续章节应保留此前的报告。

```bash
# 先配置好构建与运行环境
$ git clone https://github.com/LearningOS/rCore-Tutorial-Checker.git ci-user
$ git clone https://github.com/LearningOS/rCore-Tutorial-Test.git ci-user/user
$ git checkout ch$ID
# 使用更完整的测试用例检查并评测 ch$ID 中的操作系统
$ make -C ci-user test CHAPTER=$ID
```

注意：`$ID` 的取值范围为 [3,4,5,6,8]。

## 提交与查看成绩

完成代码和实验报告后，使用领取仓库的 GitHub 账号推送到对应的 `ch3`、`ch4`、`ch5`、`ch6` 或 `ch8` 分支。在 Actions 中查看测试与上传结果，再到 OpenCamp 查看成绩。`main`、`ch1`、`ch2`、`ch7` 不计分；每个计分章节通过后计 100 分，累计最高 500 分。
