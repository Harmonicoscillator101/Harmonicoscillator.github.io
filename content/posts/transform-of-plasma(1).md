---
title: "等离子体输运理论(1)"
date: 2026-07-29
draft: false
math: true
tags: ["等离子体", "输运理论", "理论力学","笔记"]
categories: ["物理"]
---

# Hamilton力学:从正则变换到赝正则变换

## Hamilton正则方程与正则变换

在经典Hamilton力学中，自由度为 $s$ 的系统需要规定 $2s$ 个变量，我们在理论力学课程中知道它们是广义坐标 $q_i\ (i=1,2,\dots,s)$ 和广义动量 $p_i\ (i=1,2,\dots,s)$。假设Hamilton函数 $H$ 不显含时间，这样的系统被称为自洽系统。系统的运动满足Hamilton正则方程：
$$\dot{q}_i=\frac{\partial H(q,p)}{\partial p_i},\quad \dot{p}_i=-\frac{\partial H(q,p)}{\partial q_i}\tag{1}$$
这样，$q$ 与 $p$ 成为了动力学系统的固定相空间的变量。实际上，上式也可以改写为矩阵的形式。设坐标与动量组成的向量 $\vec{\eta}=(q,p)^T$，那么正则方程：
$$\dot{\eta}=\begin{pmatrix}\frac{\partial H}{\partial p}\\ -\frac{\partial H}{\partial q}\end{pmatrix} =\begin{pmatrix} 0 & \mathbf{I}_s \\ -\mathbf{I}_s & 0 \end{pmatrix} \begin{pmatrix}\frac{\partial H}{\partial q}\\ \frac{\partial H}{\partial p}\end{pmatrix} =\mathbf{\sigma}\frac{\partial H}{\partial\eta}\tag{2}$$
其中 $\mathbf{I}_s$ 是 $s\times s$ 单位矩阵。

由于Hamilton动力学中广义坐标与广义动量处于对等的地位，因此可以考虑更加广义的变换，即从 $(q_i,p_i)$ 到 $(Q_i,P_i)$ 的一种变换，满足：
$$Q_i=Q_i(q,p),\quad P_i=P_i(q,p)\tag{3}$$
我们要求变换后的动力学方程仍然满足Hamilton正则方程，满足这一要求的变换就称为正则变换。特别指出，变化后的两组变量 $P_i$ 与 $Q_i$ 完全对等，不需要区分哪个是坐标哪个是动量。

## Poisson括号

用Poisson括号来表示正则变换更加简便，也更加具有对称美感。

对于不含时的力学量 $\phi(p,q)$ 的时间变化率为
$$\frac{\mathrm{d}\phi}{\mathrm{d}t} =\sum_{i=1}^s\left(\frac{\partial\phi}{\partial q_i}\frac{\partial H}{\partial p_i} -\frac{\partial \phi}{\partial p_i}\frac{\partial H}{\partial q_i}\right)\tag{4}$$
定义这两个力学量 $\phi$ 与 $H$ 的Poisson括号为：
$$[\phi ,H]=\sum_{i=1}^s\left(\frac{\partial\phi}{\partial q_i}\frac{\partial H}{\partial p_i} -\frac{\partial \phi}{\partial p_i}\frac{\partial H}{\partial q_i}\right)\tag{5}$$
因此，由于系统的运动，任意动力学函数随着时间演化都可以由方程
$$\dot{\phi}=[\phi,H]\tag{6}$$
得到，这就是Hamilton体系中运动方程的最普遍形式。那么Hamilton正则方程就可以表示为：
$$\dot{p}_i=[p_i,H],\quad \dot{q}_i=[q_i,H]\tag{7}$$

容易验算其满足：

$$[q_i,q_j]=0,\quad [p_i,p_j]=0,\quad [q_i,p_j]=\delta_{ij}\tag{8}$$
其中 $\delta_{ij}$ 是Kronecker符号。

在1.1中，变换 $Q_i=Q_i(q,p),P_i=P_i(q,p)$ 满足正则变换，因此有
$$[Q_i,Q_j]=0,\quad [P_i,P_j]=0,\quad [Q_i,P_j]=\delta_{ij}\tag{9}$$
这些关系的一个推论是其Jacobi行列式等于1。从一个自由度的情况验证它：
$$[Q,P]=\begin{vmatrix} \frac{\partial Q}{\partial q} & \frac{\partial Q}{\partial p} \\[6pt] \frac{\partial P}{\partial q} & \frac{\partial P}{\partial p} \end{vmatrix}=J=1.\tag{10}$$

## Lie括号

实际上，Poisson括号是Lie括号在正则变换时的特殊情况。在此有必要介绍一下Lie括号为下文的赝正则变换引入。

在Hamilton力学中，所有物理量都定义为 $(q,p)$ 相空间的函数，或许还依赖于某些被称为动力学函数的外参量 $a,b,\dots$，如时间 $t$，质量 $m$，电荷 $e$，磁场 $B$，光速 $c$ 等等，它们可以统一表示为：
$$a=a(q,p;\alpha)\tag{11}$$

考虑所有动力学函数的集合 $\mathcal{D}$，并赋予这个集合一个代数结构，并且满足线性组合的封闭性。此外，乘法与逆运算的结果同样在集合中。
$$a\alpha+b\beta=d,\quad d\in \mathcal{D}\tag{12}$$
$$a\cdot b=e,\quad e\in \mathcal{D}\tag{13}$$
$$a^{-1}=f,\quad f\in \mathcal{D}\tag{14}$$
这样的运算具有通常的代数和几何意义。但是真正的核心性质在于定义一个新符号：Lie括号。它可以被描述为：

$$
\begin{aligned}
\left[a(q,p),b(q,p)\right]
&=\sum_{i=1}^{f}\sum_{j=1}^{f}
\Biggl(
\frac{\partial a}{\partial q_i}
\frac{\partial b}{\partial q_j}[q_i,q_j]
\\
&\quad+
\frac{\partial a}{\partial q_i}
\frac{\partial b}{\partial p_j}[q_i,p_j]
+
\frac{\partial a}{\partial p_i}
\frac{\partial b}{\partial q_j}[p_i,q_j]
+
\frac{\partial a}{\partial p_i}
\frac{\partial b}{\partial p_j}[p_i,p_j]
\Biggr).
\end{aligned}
\tag{15}
$$

$$[a,b]=g,\quad g\in \mathcal{D}\tag{16}$$
$$[a,b]=-[b,a]\tag{17}$$
$$[\alpha a+\beta b,c]=\alpha[a,c]+\beta[b,c]\tag{18}$$
$$[ab,c]=a[b,c]+b[a,c]\tag{19}$$
且有Jacobi恒等式关系：
$$[[a,b],c]+[[b,c],a]+[[c,a],b]=0\tag{20}$$
我们惊讶地发现，这些性质和运算方法都是Poisson括号所具备的。进一步考察，当式(15)满足正则变换(7)时，它就退化成了Poisson括号的形式(4)。可以说Poisson括号是Lie括号的一个特殊形式。实际上，Lie括号与向量空间共同构成了Lie代数结构，但是过于繁复的数学内容会让人焦头烂额，所以我并没有深入学习Lie代数。

## 赝正则变换

现在我们可以进入正题：什么是赝正则变换？在实际中，要求物理应用上方便又满足正则共轭的变量经常是困难的，比如 $Q=q,\;P=2p$ 这样非常简单的变换就不是正则变换。为了研究的普遍性，应当给出更加广义的变换。

引入任意且可逆的变换：
$$Q_i=Q_i(q,p),\quad P_i=P_i(q,p)\tag{21}$$
但是这个变换不满足正则变换，即不满足式(8)。但是Lie括号的基本运算规则允许我们可以重新定义新变量的Lie括号。

$$\begin{cases} [Q_{i},Q_{j}] = \mathcal{F}_{ij}(Q,P),\\[4pt] [P_{i},P_{j}] = \mathcal{G}_{ij}(Q,P),\\[4pt] [Q_{i},P_{j}] = \mathcal{H}_{ij}(Q,P), \end{cases} \qquad i,j=1,2,\cdots,f.\tag{22}$$

这些括号运算仍然满足Lie括号的基本法则，只不过其结果不再是平凡的 $0$ 或者 $1$，而是非平凡的动力学函数，即1.3中的 $a,b,\dots$。作者称满足(22)的变换为赝正则变换，不难发现正则变换是赝正则变换的特例。因此，式(15)可以整理为

$$\begin{aligned} [a(Q,P),b(Q,P)] &= \sum_{i=1}^{f} \sum_{j=1}^{f} \Bigl( \frac{\partial a}{\partial Q_{i}} \frac{\partial b}{\partial Q_{j}} \mathcal{F}_{ij}(Q,P) \\ &\quad + \left( \frac{\partial a}{\partial Q_{i}} \frac{\partial b}{\partial P_{j}} - \frac{\partial a}{\partial P_{j}} \frac{\partial b}{\partial Q_{i}} \right) \mathcal{H}_{ij}(Q,P) \\ &\quad + \frac{\partial a}{\partial P_{i}} \frac{\partial b}{\partial P_{j}} \mathcal{G}_{ij}(Q,P) \Bigr) \end{aligned}\tag{23}$$

运动方程的形式仍然符合Hamilton的形式体系：
$$\dot{Q}_{i}= [Q_{i},H(Q,P)],\qquad \dot{P}_{i}= [P_{i},H(Q,P)].\tag{24}$$
或者：
$$\begin{cases} \dot{Q}_{i} = \displaystyle\sum_{j=1}^{f} \Bigl( \mathcal{F}_{ij}(Q,P) \frac{\partial H(Q,P)}{\partial Q_{j}} + \mathcal{H}_{ij}(Q,P) \frac{\partial H(Q,P)}{\partial P_{j}} \Bigr), \\[8pt] \dot{P}_{i} = \displaystyle\sum_{j=1}^{f} \Bigl( -\mathcal{H}_{ij}(Q,P) \frac{\partial H(Q,P)}{\partial Q_{j}} + \mathcal{G}_{ij}(Q,P) \frac{\partial H(Q,P)}{\partial P_{j}} \Bigr). \end{cases}\tag{25}$$
这样，我们完成了Hamilton方程对一组非正则变量的推广。（实际上，在普遍的Hamilton正则变换中，$Q$ 和 $P$ 对应的Hamilton量 $K$ 与原来的相差一个 $\partial U/\partial t$，但是我们考虑的不显含时间 $t$）

赝正则变换丧失了式(10)的Jacobi行列式的性质，取而代之的是更加广义的结果。仍然引入二维矢量：$\vec{\gamma}=(q,p)^T$，$\vec{\Gamma}=(Q,P)$。对正则变换，$\vec{\gamma}$ 满足式(2)，但是对于赝正则变换，需要一个更加复杂的矩阵，定义为：
$$\Sigma = \begin{pmatrix} \mathcal{F} & \mathcal{H} \\ -\mathcal{H}^T & \mathcal{G} \end{pmatrix},\tag{26}$$
其中的矩阵元由式(22)确定。其中 $\sigma$ 与 $\Sigma$ 矩阵的关系可以由下式得到：
$$\Sigma^{ij}=[\Gamma^i,\Gamma^j] =\sum_{m}\sum_n \frac{\partial\Gamma^i}{\partial\gamma^m} \sigma^{mn} \frac{\partial\Gamma^j}{\partial\gamma^n}\tag{27}$$
计算两端的行列式有：
$$\| \Sigma \| = \| \sigma \| \left( \left\| \frac{\partial \Gamma^{k}}{\partial \gamma^{m}} \right\| \right)^{2},\tag{28}$$
且：
$$\|\sigma\|=1,\qquad \left\| \frac{\partial \Gamma^k}{\partial \gamma^m} \right\| = \frac{1}{J}\tag{29}$$
因此可以得到
$$J^2 = \frac{1}{\|\Sigma\|}.\tag{30}$$