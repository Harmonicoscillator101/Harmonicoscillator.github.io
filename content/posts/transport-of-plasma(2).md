---
title: "等离子体输运理论(2)"
date: 2026-07-29
draft: false
math: true
tags: ["等离子体", "输运理论","笔记"]
categories: ["物理"]
---
## 局域坐标系

这同样是非常基础但是重要的一节。区别于固定的笛卡尔坐标系引入了一种动态坐标系，从而更简便地描述电磁学的场线等。

### Frenet坐标系

对于三维空间的任意一条光滑的曲线，取其上任意一点，可以构造三个相互垂直的单位向量：

1.切向量 $\boldsymbol{b}(\boldsymbol{r})$。其方向指向曲线在该点的前进方向,可以由原点到该点的位置矢量 $\boldsymbol{r}(s)$ 对自然参量 $s$（也就是弧长）的一阶导数来表示：
$$\frac{\mathrm{d}\boldsymbol{r}(s)}{\mathrm{d}s}=\boldsymbol{b}(\boldsymbol{r}(s))\tag{1}$$

2.法向量 $\boldsymbol{N}(\boldsymbol{r})$。其方向指向曲线这一小段圆弧的圆心，与切向量垂直。定义曲率矢量，用以描述切向量的方向变化程度：
$$\boldsymbol{k}(s)=\frac{\mathrm{d}\boldsymbol{b}(\boldsymbol{r})}{\mathrm{d}s}=\frac{\mathrm{d}^2\boldsymbol{r}(s)}{\mathrm{d}s^2}\tag{2}$$
则曲率矢量的长度 $k$、曲率半径 $\rho$ 的关系为：
$$k=\frac{1}{\rho}=\left|\frac{\mathrm{d}\boldsymbol{b}(\boldsymbol{r})}{\mathrm{d}s}\right|\tag{3}$$
那么单位法向量就可以写为：
$$\boldsymbol{N}(\boldsymbol{r})=\frac{1}{k}\boldsymbol{k}(s)=\rho\boldsymbol{k}(s)\tag{4}$$

3.副法向量 $\boldsymbol{\beta }(\boldsymbol{r})$。其定义为上述两个单位向量的叉积：
$$\boldsymbol{\beta}(\boldsymbol{r})=\boldsymbol{b}(\boldsymbol{r})\times \boldsymbol{N}(\boldsymbol{r})\tag{5}$$
我们可以定义挠率 $\kappa$ 来表示曲线离开其所在平面的度量，反应副法线方向变化的速率，其矢量形式定义为：
$$\boldsymbol{\kappa}=\frac{\mathrm{d}\boldsymbol{\beta}(\boldsymbol{r})}{\mathrm{d}s}=\frac{1}{\tau}\boldsymbol{N}(\boldsymbol{r})\tag{6}$$
其中 $\tau$ 为挠率半径。

### Frenet公式

在此之前，先考虑一个任意的场量 $F(\boldsymbol{r}(s))$，对其求自然参量的一阶导数可以得到：
$$\frac{\mathrm{d}F(\boldsymbol{r})}{\mathrm{d}s}=\frac{\mathrm{d}\boldsymbol{r}(s)}{\mathrm{d}s}\cdot\frac{\partial F(\boldsymbol{r})}{\partial\boldsymbol{r}}=[\boldsymbol{b}(\boldsymbol{r})\cdot \nabla ]F(\boldsymbol{r})\tag{7}$$
那就好办了，前面类似的定义都可以重写，比如式(33)可以写为：
$$\frac{1}{\rho}=|(\boldsymbol{b}\cdot\nabla)\boldsymbol{b}|\tag{8}$$
而挠率半径可以由下式定义：
$$\kappa=\frac{1}{\tau}=\boldsymbol{N}\cdot[(\boldsymbol{b}\cdot \nabla)\boldsymbol{\beta}]\tag{9}$$
因此我们可以写出Frenet公式：
$$
\begin{split}
\frac{d \boldsymbol{b} \left( s \right)}{ds}= \left( \boldsymbol{b} \cdot \nabla \right) \boldsymbol{b}= \frac{1}{ \rho}\boldsymbol{N}, \\
\frac{d \boldsymbol{N} \left( s \right)}{ds}= \left( \boldsymbol{b} \cdot \nabla \right) \boldsymbol{N}=- \frac{1}{ \tau} \boldsymbol{\beta}- \frac{1}{ \rho}\boldsymbol{b}, \\
\frac{d \boldsymbol{ \beta} \left( s \right)}{ds}= \left( \boldsymbol{b} \cdot \nabla \right) \boldsymbol\beta= \frac{1}{ \tau}\boldsymbol{N}.
\end{split}
\tag{10}
$$
需要指出，作者这里给出的Frenet公式与常见的公式存在正负号的一些差异，这是由于定义的问题,不影响物理图像。

对于一个基本的、存在梯度的磁场，$\boldsymbol{b}(\boldsymbol{r})$ 的方向是确定的，但是另外两个矢量则会在与其垂直的平面上方向不定。这时定义新的两个矢量：
$$\boldsymbol{N}'(\boldsymbol{r})=\frac{\boldsymbol{b}\times \nabla B(\boldsymbol{r})}{|\nabla B(\boldsymbol{r})|}\tag{11}$$
$$\boldsymbol{\beta}'(\boldsymbol{r})=\boldsymbol{b}\times \boldsymbol{N}'\tag{12}$$
这样由磁场的几何结构再次构造了一个局域坐标系。

但是，对于均匀场或者场处处平行于 $\boldsymbol{b}$ 时，此时无法再通过式(41)与(42)构造局域坐标系，不如直接采取绝对参考系来的方便。

## 单个带电粒子在电磁场的运动

### 粒子在不均匀定态电磁场中运动

带电量为 $e$ 的粒子在电磁场中受 Lorentz 力为：
$$\boldsymbol{F} = e \left( \boldsymbol{E} + \boldsymbol{v} \times \boldsymbol{B} \right)\tag{13}$$

引入矢势 $\boldsymbol{A}(\boldsymbol{q}, t)$ 和标势 $\varphi(\boldsymbol{q}, t)$：
$$
\begin{aligned}
\boldsymbol{B} &= \nabla \times \boldsymbol{A} \\
\boldsymbol{E} &= - \nabla \varphi - \frac{\partial \boldsymbol{A}}{\partial t}
\end{aligned}
\tag{14}
$$

由于场是定态的，所以 $\frac{\partial \boldsymbol{A}}{\partial t} = 0$。则有：
$$
\begin{aligned}
\boldsymbol{F} &= e \left[ - \nabla \varphi + \boldsymbol{v} \times (\nabla \times \boldsymbol{A}) \right] \\
       &= e \left[ - \nabla \varphi + \nabla (\boldsymbol{v} \cdot \boldsymbol{A}) - (\boldsymbol{v} \cdot \nabla) \boldsymbol{A} \right] \\
       &= - \nabla \left( e \varphi - e \boldsymbol{A} \cdot \boldsymbol{v} \right)
\end{aligned}
\tag{15}
$$

因此可定义广义势能：
$$U(q, \dot{q}) = e \varphi - e \boldsymbol{A} \cdot \boldsymbol{v}\tag{16}$$

因此我们有推广的 Lagrange 量：
$$L = T - U = \frac{1}{2} m \boldsymbol{v}^2 - (e \varphi - e \boldsymbol{A} \cdot \boldsymbol{v})\tag{17}$$

广义动量：
$$p_x = \frac{\partial L}{\partial v_x} = m v_x + e A_x\tag{18}$$

Hamilton 量为：
$$H = \boldsymbol{p} \cdot \boldsymbol{v} - L = \frac{1}{2m} \left( \boldsymbol{p} - e \boldsymbol{A} \right)^2 + e \varphi\tag{19}$$
其中 $\boldsymbol{A} = \boldsymbol{A}(\boldsymbol{q})$，$\varphi = \varphi(\boldsymbol{q})$。这样我们可以给出 Hamilton 运动方程与 Poisson 括号表示：
$$
\begin{cases}
\dot{q}_i = \frac{\partial H}{\partial p_i} = \frac{1}{m} \left( p_i - e A_i \right) \\
\dot{p}_i = - \frac{\partial H}{\partial x_i} = \frac{e}{m} \left( p_j - e A_j \right) \frac{\partial A_j}{\partial x_i} - e \frac{\partial \varphi}{\partial x_i}
\end{cases}
\tag{20}
$$

$$\{ q_i, q_j \} = 0, \quad \{ p_i, p_j \} = 0, \quad \{ q_i, p_j \} = \delta_{ij}\tag{21}$$

很标准，但是我们发现这里的正则变量并不方便。原因在于动量 $\boldsymbol{p}$ 并不具备直观的物理意义。当它转换为机械动量 $\boldsymbol{\Pi} = m\boldsymbol{v}$ 才是直观的，那么它可以被如下变换：
$$\boldsymbol{\Pi} = m\boldsymbol{v} = \boldsymbol{p} - e\boldsymbol{A}\tag{22}$$

所以我们可以作这样的变换：$(q,p) \rightarrow (q,v)$ 然而这并不是正则变换。比如：
$$\{q_1, v_1\} = \sum_{k=1}^3 \left( \frac{\partial q_1}{\partial q_k} \frac{\partial v_1}{\partial p_k} - \frac{\partial q_1}{\partial p_k} \frac{\partial v_1}{\partial q_k} \right) = \frac{1}{m}\tag{23}$$

这并不等于简单的0或1。所以我们要应用赝正则变换的处理方法，依次计算Lie括号、Jacobi行列式、新变量的Hamilton函数以及运动方程：
$$\{q_i, q_j\} = 0, \quad \{q_i, v_j\} = \frac{1}{m}\delta_{ij}, \quad \{v_i, v_j\} = \frac{e}{m^2}\varepsilon_{ijk}B_k\tag{24}$$
$$J = m^3\tag{25}$$
$$H = \frac{1}{2}m\boldsymbol{v}^2 + e\varphi\tag{26}$$
$$\dot{\boldsymbol{q}} = \boldsymbol{v}\tag{27}$$

$$\dot{\boldsymbol{v}} = \frac{e}{m}(\boldsymbol{v} \times \boldsymbol{B}) + \frac{e}{m}\boldsymbol{E} \Rightarrow \dot{v}_i = \frac{e}{m}\varepsilon_{ijk}v_jB_k - \frac{e}{m}\frac{\partial \varphi}{\partial x_i}\tag{28}$$
很有意思的一点是，对能量 $H$ 无贡献的磁场 $\boldsymbol{B}$ 可以进入运动方程。这是由于计算赝正则变换的Lie括号导致的：
$$
\begin{aligned}
\dot{v}_i &= \{v_i, H\} = m v_j\{v_i, v_j\} + e\frac{\partial \varphi}{\partial x_j}\{v_i, q_j\} \\
&= \frac{e}{m}\varepsilon_{ijk}v_jB_k - \frac{e}{m}\frac{\partial \varphi}{\partial x_i}
\end{aligned}
\tag{29}
$$

由于 Lorentz 力只作用于垂直磁场方向的分量 $v_\perp$，将速度写成平行和垂直于磁场 $\boldsymbol{B}$ 的分量 $v_\parallel$ 与 $v_\perp$，因此可推导出两个分量的运动方程。所以这里可以运用局域坐标系的方法或采用以 $\boldsymbol{r}$ 点处的 Frenet 坐标系来求其分量：设 $t$ 时刻粒子以速度 $\boldsymbol{v}$ 通过点 $\boldsymbol{r} = \boldsymbol{q}$，速度可以分解为平行于和垂直于 $\boldsymbol{B}$ 的两个分量（$\boldsymbol{r}$ 处磁场线的 Frenet 坐标系的基础单位向量）：
$$\boldsymbol{v} = v_{\parallel} \boldsymbol{b} + v_{\perp} \boldsymbol{n}_1\tag{30}$$
选择一个单位矢量 $\boldsymbol{n}_1$ 沿着 $v_\perp$ 方向，第二个单位向量 $\boldsymbol{n}_2$，为 $\boldsymbol{n}_2$ 和 $\boldsymbol{b}$ 张成平面的法向单位向量，则有 $\boldsymbol{n}_1 \times \boldsymbol{n}_2 = \boldsymbol{b}$，将其叫作运动局域坐标系。

不妨回顾之前的 Frenet 坐标系。$\boldsymbol{N}(\boldsymbol{r})$ 指向场线 $\boldsymbol{\beta}(\boldsymbol{r})$（此处考虑 $\boldsymbol{B}(\boldsymbol{r})$）的曲线切向，$\boldsymbol{N}(\boldsymbol{r})$ 为曲线弧内侧的法向量，$\boldsymbol{\beta}(\boldsymbol{r})$ 为上述两坐标系向量张成平面的法向量。

为什么要引入局域参考系？因为 Frenet 系是描述磁场线几何，而运动坐标系是描述粒子运动的！在此处，两个坐标系共用 $\boldsymbol{b}(\boldsymbol{r})$，那么剩下两个向量的变换用一个简单的旋转矩阵描述：

$$
\begin{aligned}
\begin{pmatrix}
\boldsymbol n_1\\
\boldsymbol n_2
\end{pmatrix}
&=
\begin{pmatrix}
-\sin\theta&-\cos\theta\\
\cos\theta&-\sin\theta
\end{pmatrix}
\begin{pmatrix}
\boldsymbol N\\
\boldsymbol\beta
\end{pmatrix}
\end{aligned}
$$

$\theta$ 定义为 $\boldsymbol{n}_2$ 与 $\boldsymbol{N}$ 之间的夹角（它比普通的旋转矩阵多了一个 $\frac{\pi}{2}$），我们认为作者这样定义略有麻烦，但物理直观是一样的）

以及
$$\frac{\partial \boldsymbol{n}_1}{\partial \theta} = - \boldsymbol{n}_2, \quad \frac{\partial \boldsymbol{n}_2}{\partial \theta} = \boldsymbol{n}_1\tag{32}$$
这样有用的关系。

又因为
$$\boldsymbol{v} = v_{\parallel} \boldsymbol{b} + v_{\perp} \boldsymbol{n}_1\tag{33}$$

我们可以从 4 个变量来作分析，它们分别是 $\boldsymbol{q}$, $v_{\parallel}$, $v_{\perp}$ 和 $\theta$。

其中 $\theta$ 为回旋相角，而 $v_{\perp}$ 是非负的，$v_{\parallel}$ 可正可负。这样，由 $(\boldsymbol{q}, \boldsymbol{v}) \rightarrow (\boldsymbol{q}, v_{\parallel}, v_{\perp}, \theta)$ 的变换可以通过赝正则变换来处理。这样就有七个 Lie 括号，虽然有点麻烦，但都从基本的法则出发就可以得到。

定义：
$$\boldsymbol{q} = \boldsymbol{q}, \quad \boldsymbol{v} = v_{\parallel} \boldsymbol{b} + v_{\perp} \boldsymbol{n}_1\tag{34}$$
其中 $\boldsymbol{b} = \boldsymbol{b}(\boldsymbol{q})$, $\boldsymbol{n}_1 = \boldsymbol{n}_1(\boldsymbol{q}, \theta)$

Lie 括号：
$$\{q_i, q_j\} = 0, \quad \{\boldsymbol{q}, v_{\parallel}\} = \frac{1}{m} \boldsymbol{b}, \quad \{\boldsymbol{q}, v_{\perp}\} = \frac{1}{m} \boldsymbol{n}_1\tag{35}$$

$$\{\boldsymbol{q}, \theta\} = -\frac{1}{mv_{\perp}} \boldsymbol{n}_2, \quad \{v_{\parallel}, v_{\perp}\} = \frac{1}{m} \boldsymbol{n}_2 \cdot \boldsymbol{D},\tag{36}$$

$$\{v_{\parallel}, \theta\} = \frac{1}{mv_{\perp}} \boldsymbol{n}_1 \cdot \boldsymbol{D}, \quad \{v_{\perp}, \theta\} = -\frac{eB}{m^2 v_{\perp}} - \frac{1}{mv_{\perp}} \boldsymbol{b} \cdot \boldsymbol{D}\tag{37}$$
其中 $\boldsymbol{D} = v_{\parallel}(\nabla \times \boldsymbol{b}) + v_{\perp}(\nabla \times \boldsymbol{n}_1)$

Hamilton 函数
$$H = \frac{1}{2} m (v_{\perp}^2 + v_{\parallel}^2) + e \varphi (\boldsymbol{q})\tag{38}$$

运动方程
$$\dot{\boldsymbol{q}} = v_{\perp} \boldsymbol{n}_1 + v_{\parallel} \boldsymbol{b},\tag{39}$$

$$\dot{v}_{\parallel} = v_{\perp} \boldsymbol{n}_2 \cdot \boldsymbol{D} + \frac{e}{m} \boldsymbol{b} \cdot \boldsymbol{E},\tag{40}$$

$$\dot{v}_{\perp} = -v_{\perp} \boldsymbol{n}_2 \cdot \boldsymbol{D} + \frac{e}{m} \boldsymbol{n}_1 \cdot \boldsymbol{E},\tag{41}$$

$$\dot{\theta} = \frac{eB}{m} + \boldsymbol{b} \cdot \boldsymbol{D} - \frac{v_{\parallel}}{v_{\perp}} \boldsymbol{n}_1 \cdot \boldsymbol{D} - \frac{e}{mv_{\perp}} \boldsymbol{n}_2 \cdot \boldsymbol{E}\tag{42}$$

这三组变量 $(\boldsymbol{p},\boldsymbol{q}) \Leftrightarrow (\boldsymbol{q},\boldsymbol{v}) \Leftrightarrow (\boldsymbol{q},v_{\parallel},v_{\perp},\theta)$ 被作者称为粒子变量，因其均含有位置矢量 $\boldsymbol{q}$。（笔者认为，$(\boldsymbol{q},\boldsymbol{p})$ 与 $(\boldsymbol{q},\boldsymbol{v})$ 之间的变换最为重要）

### 简单的实例：单个带电粒子在均匀磁场中的运动

均匀电场、无磁场的情况平凡，不详述。
对于 $\boldsymbol{E}=0$，均匀磁场的条件下，广义动量 $\boldsymbol{p}$ 是恒定的，而 $\boldsymbol{v}$ 与 $\boldsymbol{q}$ 不再依赖。它简化为
$$\boldsymbol{v} = v_{\parallel} \boldsymbol{b} + v_{\perp} \boldsymbol{n}_1(\theta)\tag{43}$$
所以运动方程简化为：
$$\dot{\boldsymbol{q}} = v_{\parallel} \boldsymbol{b} + v_{\perp} \boldsymbol{n}_1, \quad \dot{v}_{\parallel} = 0, \quad \dot{v}_{\perp} = 0, \quad \dot{\theta} = \omega\tag{44}$$
其中 $\omega$ 为 Larmor 频率，$\omega = \frac{eB}{m}$。$\omega$ 的正负取决于 $e$。

相角 $\theta$ 随时间变化：
$$\theta = \theta_0 + \omega t\tag{45}$$
将其代入位置矢量的方程，平行方向是简单的
$$q_{\parallel}(t) = q_{\parallel 0} + v_{\parallel} t\tag{46}$$
但对垂直分量，略微复杂。

$$\boldsymbol{q}_{\perp} = \int v_{\perp} \boldsymbol{n}_1 dt = v_{\perp} \int \boldsymbol{n}_1 dt\tag{47}$$
又 $\theta = \theta_0 + \omega t$，则 $dt = \frac{d\theta}{\omega}$，且 $\frac{\partial \boldsymbol{n}_1}{\partial \theta} = -\boldsymbol{n}_2$

$$\boldsymbol{q}_{\perp} = \frac{v_{\perp}}{\omega} \int \boldsymbol{n}_1 d\theta = \frac{v_{\perp}}{\omega} (\boldsymbol{n}_2(\theta) - \boldsymbol{n}_2(\theta_0)) + \boldsymbol{q}_{\perp 0}\tag{48}$$
可见 $\boldsymbol{q}_{\perp}(t)$ 是周期函数，因此可知道回旋半径为 (Larmor 半径)
$$\rho_L = \frac{v_{\perp}}{|\omega|}\tag{49}$$
回旋中心的位矢为 $\boldsymbol{Y}$
$$\boldsymbol{Y} = \boldsymbol{q}_0 - \frac{\boldsymbol{v}_{\perp}}{\omega}\boldsymbol{n}_2(\boldsymbol{q}_0,\theta_0)\tag{50}$$
只与粒子初态位置与速度有关，称为粒子导向中心。

我们可以用程序简单模拟这个模型。沿Z轴的均匀磁场 $B_z=1T$，粒子初速度为 $\boldsymbol{v}=(1\times 10^6;0.5\times 10^6;0.2\times 10^6)$,无电场，得到以下的回旋运动：

![单个电子在均匀磁场中的回旋运动](/images/单个电子在均匀磁场中的回旋运动.jpg)