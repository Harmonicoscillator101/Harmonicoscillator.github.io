---
title: "在个人Windows电脑上使用VS Code中搭建Qiskit量子计算开发环境"
date: 2026-08-07
draft: false
math: true
tags: ["量子力学", "量子计算","教程"]
categories: ["物理"]
---
# 在个人Windows电脑上使用VS Code搭建Qiskit量子计算开发环境

## 前言：什么是Qiskit

Qiskit是IBM团队开发的性能最高的开源量子计算和算法研究软件栈。构建、优化并大规模执行量子工作负载。它本身基于python，提供开源的强大工具和简化的工作流程，帮助学生和研究者开发量子计算算法并进行实验，本质上是利用经典代码来“模拟”量子电路。但是，它最强大之处在于我们在电脑上写出来的代码可以直接连接到IBM团队的超导量子计算机上，实现真正物理世界中的量子计算。这当然不是免费的，每个用户每周有10分钟的免费时间，再往后就要收费了。更多详细内容可以[参见官网](https://www.ibm.com/quantum/qiskit)

我现在正在牛津大学进行Quantum Computing课程的学习，发现Qiskit不仅能辅助我理解量子计算课程内容，也有助于我完成presentation，甚至为后续工作提供便利，在网络上找了许多教程，大部分都是直接从Anaconda入手的，比如[知乎答主christorange的文章](https://zhuanlan.zhihu.com/p/414399506)等，都是不错的配置方案，不过考虑到我们可以直接用VScode使用uv来pip下载Qiskit以及其他所需要的一切，所以这里再提供一个方法。

## 正式开始：你所需要的VScode编辑器

首先你需要一个VScode(全称Visual Studio Code)，这是微软开发的轻量化代码解释与编辑器，支持几乎所有语言，内含丰富的拓展内容，你可以[直接点这里下载](https://code.visualstudio.com/)(当然，下载太慢的话，可能需要镜像源了)。在这之后，直接下载以下所有Python拓展：Python (Microsoft)、Pylance、Python Debugger、Jupyter、Python Indent，以及其他你觉得有用的东西。这里只是简略地说明一下大体步骤，大部分人可能早就有VScode了，如果觉得我讲得太简略，可以参见[知乎答主李一的文章](https://zhuanlan.zhihu.com/p/698865320)、[知乎答主GIS小巫师的文章](https://zhuanlan.zhihu.com/p/678737903)等等等等，这些优秀答主都提供了超级详细的配置教程。

## 核心步骤：用uv来管理python环境

### 安装uv

uv是一个用Rust编写的极速Python包和项目管理器。它可以替代 pip, pip-tools, pipx, poetry, pyenv, virtualenv 等多个工具，并且速度比pip快10到100倍。我们可以直接从命令行或者Powershell来下载uv。搜索Powershell并运行，输入

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

验证安装，输入

```powershell
uv --version
```

当然，也可以通过pip install uv，或者直接[访问官网](https://pypi.org/project/uv/0.11.17/)进行安装。

接下来，让我们初始化python环境。初始化项目

```powershell
uv init my_qiskit_project
cd my_qiskit_project
```

创建虚拟环境：uv 会在你添加第一个依赖时自动创建虚拟环境（.venv文件夹）。也可以手动创建：

```powershell
uv venv
```

接下来，激活你的虚拟环境

```powershell
.venv\Scripts\Activate.ps1
```

### 配置VScode解释器

按 Ctrl+Shift+P 打开命令面板，输入并选择 Python: Select Interpreter。从列表中选择你的虚拟环境，路径类似于 ./.venv/Scripts/python.exe。这是确保VS Code使用你项目专属环境的关键一步。此外，很多人在激活虚拟环境后，其实并没有安装pip，我们需要额外安装(注意这里已经转移到了VScode里的终端，你首先要在VScode打开你的项目文件，然后打开终端，可以按Ctrl+`打开它。之后的操作都在这个终端里面。)：

```powershell
python -m ensurepip --upgrade
```

可以检查版本

```powershell
python --version
```

这就是安装uv并配置python环境的大致流程，如果你觉得不够详细，或者遇到困难，以下还有几篇很好的教程文章：[知乎答主四十四次日落的文章](https://zhuanlan.zhihu.com/p/1938636637249700959)，[csdn答主Balrog-v的文章](https://blog.csdn.net/2401_86720553/article/details/156489207),[csdn答主ㄣ知冷煖★的文章](https://blog.csdn.net/weixin_42475060/article/details/160434523)。

## 最终步骤：安装Qiskit并编写你的首个量子计算程序

在完全搞好你的Python环境后，你就可以正式下载Qiskit了。

```powershell
python -m pip install qiskit
```

此后，应当安装一系列方便的包：

```powershell
python -m pip install qiskit-aer
python -m pip install qiskit-ibm-runtime
python -m pip install matplotlib
python -m pip install numpy
python -m pip install "qiskit[visualization]"
python -m pip install jupyter ipykernel
python -m pip install pylatexenc
```

其中，qiskit-aer是本地高性能模拟器；qiskit-ibm-runtime是连接IBM量子计算云服务的接口；matplotlib用于数据可视化，如绘制结果柱状图;numpy这是python必装的高性能数据处理包；"qiskit[visualization]"可以更好地可视化结果；jupyter ipykernel 则允许你使用.ipynb；pylatexenc能够将结果导出为latex文本，方便写入笔记或者进行展示。

在完成这一切后，检查是否安装成功
```powershell
python -c "import qiskit; print(qiskit.__version__)"
```

以及

```powershell
python -c "from qiskit_aer import AerSimulator; print('Aer OK')"
```

如果没有报错，那么一切都大功告成了。

## 创建你的第一个Qiskit程序

在你的VScode里，或者文件夹中新建一个01_H_gate.py程序，输入如下代码

```python
from qiskit import QuantumCircuit
qc = QuantumCircuit(1)
qc.h(0)
print(qc)
```

右键选择运行python，然后选择在终端中运行python文件，然后你就会得到一个类似的方框框起来一个H的结果，那么，你就成功地创建了一个H门（Hadamard门）。

你还可以尝试Bell态，再新建一个文件02_Bell_state.py，输入：

```python
from qiskit import QuantumCircuit
qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
print(qc)
```

这样你就可以看到一个双量子比特电路，它使用一个H门和一个CNOT门，使得两个量子态产生纠缠。你还可以把最终产生的量子比特直接算出来：

```python
from qiskit import QuantumCircuit
from qiskit.quantum_info import Statevector
qc = QuantumCircuit(2)
qc.h(0)
qc.cx(0, 1)
state = Statevector.from_instruction(qc)
print(state)
```

你将会得到一个列向量，实际上就是
$$
\frac{1}{\sqrt{2}}(1\quad 0\quad 0\quad 1)^T
$$
这就是Bell纠缠态的展开形式，也就是
$$
\frac{1}{\sqrt{2}}(|00\rangle +|11\rangle)
$$

这里由于只是讲讲如何配置Qiskit，有关量子计算本身的算法，或者编写Qiskit所需要的语法，可以参考[我发布的专栏](https://www.zhihu.com/column/c_2068854252248765124)或者笔记（还在持续更新中），以及IBM的[官方文件与教程](https://qiskit.github.io/documentation/main/learning/modules/quantum-mechanics/get-started-with-qiskit)，还有开源社区的[帮助](https://github.com/didvc/qiskit-getting-started)