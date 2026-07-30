---
title: "等离子体输运理论(3)"
date: 2026-07-30
draft: false
math: true
tags: ["等离子体", "输运理论","笔记"]
categories: ["物理"]
---
# 带电粒子在电磁场中的运动及如何将其纳入Hamilton力学体系

## 均匀场下的漂移

### 回旋磁矩

对于垂直于磁场 $B$ 的一个载流线圈中，可以定义沿着轨道的平均电流为：
$$
    I=\frac{e \Omega}{2 \pi} \tag{1}
$$
根据电磁学知识，磁矩可以由电流回路表示：
$$
    \mu = IS =\frac{e \Omega \rho_L^2}{2} \tag{2}
$$
而回旋半径为 $\rho _L=v_{\perp}/\Omega$，且 $\Omega=eB/m$，
因此回旋磁矩：
$$
    \mu=\frac{mv_{\perp}^2}{2B} \tag{3}
$$
由叉乘关系，磁矩矢量 $\boldsymbol{\mu}$ 与 $\boldsymbol{B}$ 相反，因此 Larmor 回旋是抗磁的。

### 均匀场下的漂移运动

若同时存在均匀的磁场 $B$ 和电场 $E$，Lorentz 方程为
$$
    m\ddot{\boldsymbol{q}}=e(\boldsymbol{v}\times \boldsymbol{B}+\boldsymbol{E}) \tag{4}
$$
平行磁场分量：$\ddot{\boldsymbol{q}_{\parallel}}=e\boldsymbol{E}/m$，垂直磁场分量：$\ddot{\boldsymbol{q}_{\perp}}=e/m(\boldsymbol{v}\times \boldsymbol{B}+\boldsymbol{E}_{\perp})$

作者关心导心的运动，所以可以做一个伽利略变换，作出一个以速度 $\boldsymbol{w}_E$ 运动的坐标系，这个坐标系的原点实际上就是导心，则有 $\boldsymbol{q}=\boldsymbol{y}+\boldsymbol{w}_Et$，$\boldsymbol{y}$ 是新坐标系的位置矢量。得到速度和加速度后代入运动方程：
$$
    \ddot{\boldsymbol{y}}_{\perp}=\frac{e}{m}(\dot{\boldsymbol{y}}\times \boldsymbol{B}+ \boldsymbol{w}_E\times \boldsymbol{B}+\boldsymbol{E}_{\perp}) \tag{5}
$$
$$
    \ddot{\boldsymbol{y}}_{\parallel}=\frac{e}{m}\boldsymbol{E}_{\parallel} \tag{6}
$$

### 均匀场下的粒子分运动

这样，粒子的运动就可以分为三个运动：
$$
    \boldsymbol{q}(t)=q_{\parallel}\boldsymbol{b}+\boldsymbol{y}_{\perp}(t)+\boldsymbol{w}_E(t) \tag{7}
$$
第一个就是简单的匀加速运动：
$$
    q_{\parallel}(t)=q_{\parallel 0}+v_{\parallel}t+\frac{1}{2}\frac{e}{m}E_{\parallel}t^2 \tag{8}
$$
第二个是 Larmor 回旋，围绕着导心：
$$
    \boldsymbol{y}(t)=\boldsymbol{Y}+\frac{v_{\perp}}{\Omega}\boldsymbol{n}_2(\varphi_0+\Omega t) \tag{9}
$$
第三个就是垂直于电场与磁场的恒定速度的导心运动
$$
    \boldsymbol{w}_E=\frac{1}{B^2}(\boldsymbol{E}\times \boldsymbol{B}) \tag{10}
$$
这个就是电漂移运动。

## 不均匀场下的漂移运动

### 不均匀场的漂移运动

回到更普遍的不均匀场的情况。根据之前对 $(\boldsymbol{q},v_{\parallel},v_{\perp},\varphi)$ 的赝正则变换，在一般条件下的回旋相角方程：
$$
    \dot{\varphi}=\frac{eB}{m}+\boldsymbol{b}\cdot \boldsymbol{D}-\frac{v_{\parallel}}{v_{\perp}}\boldsymbol{n}_1\cdot \boldsymbol{D}-\frac{e}{mv_{\perp}}\boldsymbol{n}_2\cdot \boldsymbol{E} \tag{11}
$$
这在不均匀场中没有非常直观的物理图像，因此从比较简单的平直梯度场入手比较好处理。根据式 $\rho_L=mv_{\perp}/eB$，随着 $B$ 的变化，Larmor 半径也在改变，因此不同位置的回旋半径差异导致导心的变化。

### 特征长度

磁场梯度产生的漂移方向垂直于磁场与磁场梯度方向：
$$
    \boldsymbol{w}_{\nabla B}\sim \boldsymbol{B}\times \nabla\boldsymbol{B} \tag{12}
$$
在这个情况中，电荷相反的粒子向相反的方向漂移。现在可以先不急着给出梯度漂移速度的具体表达。

特别指出只要梯度足够小，那么漂移距离相对回旋半径来讲就足够长，通过引入特征长度：
$$
    L_H^{-1}=\frac{1}{B}|\nabla B| \tag{13}
$$
以标志导心运动轨迹，有 $L_H>\rho_L$。这样，从宏观视角来看，粒子的运动中，导心漂移更加明显，而回旋运动很小以至于可以忽略。这就要引出漂移近似的方法。

## 漂移近似：平均法

### 漂移近似：平均法

在回旋相角运动方程
$$
    \dot{\varphi}=\frac{eB}{m}+\boldsymbol{b}\cdot \boldsymbol{D}-\frac{v_{\parallel}}{v_{\perp}}\boldsymbol{n}_1\cdot \boldsymbol{D}-\frac{e}{mv_{\perp}}\boldsymbol{n}_2\cdot \boldsymbol{E}
$$
中，前两项的大小之比为：
$$
    \left|\frac{eB}{m}\right| : |\boldsymbol{b}\cdot\boldsymbol{D}| \sim \frac{v_{\perp}}{\rho_L} : \left(\frac{v_{\parallel}}{L_H}+\frac{v_{\perp}}{L_H'}\right) \tag{14}
$$
其中 $\boldsymbol{D}=v_{\parallel}(\nabla\times \boldsymbol{b})+v_{\perp}(\nabla \times \boldsymbol{n}_1)$。其中 $L_H$ 与 $L_H'$ 都是特征长度。由于 $\rho \ll L_H$ 及 $L_H'$，那么 $v_{\perp}/\rho_L$ 占据主导地位。

作者使用了一个数学技巧。他替换了 $eB/m=\Omega \to \frac{1}{\epsilon}\Omega$，其中 $\epsilon$ 为标度参量，是一个数量级的指示符号，将其代入动力学方程，Hamilton 函数是一致的。实际上，这个技巧可以给出很好的物理图像。当 $\epsilon \ll 1$ 时候，$v_{\perp}/\rho _L$ 显著，符合漂移近似。

### 平均法的数学处理

动力学方程具体形式：
$$
    \dot{\boldsymbol{q}}=v_{\parallel}\boldsymbol{b}(\boldsymbol{q})+v_{\perp}\boldsymbol{n}_1(\boldsymbol{q},\varphi) \tag{15}
$$
$$
    \dot{v}_{\parallel}=v_{\perp}\boldsymbol{n}_2\cdot \boldsymbol{D}+\frac{e}{m}\boldsymbol{b}\cdot\boldsymbol{E} \tag{16}
$$
$$
    \dot{v}_{\perp}=-v_{\perp}\boldsymbol{n}_2\cdot \boldsymbol{D}+\frac{e}{m}\boldsymbol{n}_1\cdot \boldsymbol{E} \tag{17}
$$
$$
    \dot{\varphi}=\frac{1}{\epsilon}\Omega+\boldsymbol{b}\cdot\boldsymbol{D}-\frac{v_{\parallel}}{v_{\perp}}\boldsymbol{n}_1\cdot \boldsymbol{D}-\frac{e}{mv_{\perp}}\boldsymbol{n}_2\cdot\boldsymbol{E} \tag{18}
$$

对于其中的三个慢变量 $x_t=\{q,v_{\perp},v_{\parallel}\}$ 的运动微分方程可以写为：
$$
    \dot{x}_t=f_k(x_t,\varphi) \tag{19}
$$
对于快变量 $\varphi$，其运动方程可以写为
$$
    \dot{\varphi}=\frac{1}{\epsilon}\Omega+a(x_t,\varphi) \tag{20}
$$
其中，$f_k(x_t,\varphi)$ 与 $a(x_t,\varphi)$ 是关于 $\varphi$ 的周期函数。

### 消除振荡项（一）

作者引用 Kruskal 的话，认为运动方程依赖于回旋相角会导致无法精细地描述运动过程，因为 $a(x_t,\varphi)$ 可能会突然涨落、净漂移率不明显，需要引入一种无限可微的变换形式，并且去除依赖关系。

用新变量 $(\xi_k,\phi)$ 替换 $(x_k,\varphi)$，这两个变量相差足够小，其满足的微分方程不包含迅速变化的相角。

$$
    x_k = \xi_k + \epsilon g_{1k}(\xi, \phi) + \epsilon^2 g_{2k}(\xi, \phi) + \cdots, \tag{21}
$$
$$
    \varphi = \phi + \epsilon q_1(\xi, \phi) + \epsilon^2 q_2(\xi, \phi) + \cdots, \tag{22}
$$
使得
$$
\frac{d\xi_k}{dt} = F_{0k}(\xi_i) + \epsilon F_{1k}(\xi_i) + \epsilon^2 F_{2k}(\xi_i) + \cdots,
$$
$$
\frac{d\phi}{dt} = \frac{1}{\epsilon} \Omega(\xi_i) + \omega_0(\xi_i) + \epsilon \omega_1(\xi_i) + \cdots.
$$

### 消除振荡项（二）

略去麻烦的计算内容，得到：
$$
    F_{0k}(\xi_i) + \frac{\partial g_{1k}(\xi_i, \phi)}{\partial \phi} \Omega (\xi_i) = f_k(\xi_i, \phi) \tag{23}
$$
对周期型的作用量取平均的方法：
$$
    \overline{G}(\xi,\phi)=\frac{1}{2\pi}\int_0^{2\pi}G(\xi,\phi)d\phi \tag{24}
$$
那么它将被分为一个平均项与一个振荡项：
$$
    G(\xi,\phi)=\tilde{G}(\xi)+\tilde{G}(\xi,\phi) \tag{25}
$$
由于周期运动，振荡项为 0。这与位力定理的思想一致。为了让式 (23) 与 (24) 更加简单，我们对它们做平均消除 $g_{ik}$ 与 $q_{i}$ 项，则有 $\xi=\overline{x}_k+\boldsymbol{O}(\epsilon^2)$，$\phi=\overline{\varphi }+\boldsymbol{O}(\epsilon)$，以及近似运动方程：
$$
    \dot{ \xi}_{k}=f_{k} \left( \xi_{1} \right), \quad \dot{ \phi}= \frac{1}{ \epsilon} \Omega \left( \xi_{1} \right). \tag{26}
$$

### 导心运动（一）

我们在之前的那个运动参考系里面研究导心：
$$
    \boldsymbol{y}=\boldsymbol{q}- \epsilon \frac{v_{ \perp}}{ \Omega \left( \boldsymbol{q} \right)}\boldsymbol{n}_{2} \left( \boldsymbol{q}, \varphi \right). \tag{27}
$$
由 Lie 括号得到运动方程（该方程未编号）：
$$
\begin{aligned}
\dot{\boldsymbol{y}} = &\left[ \boldsymbol{q} - \epsilon \frac{v_1}{\Omega(q)} \boldsymbol{n}_2(\boldsymbol{q}, \varphi), H \right] \\
= &v_1 \boldsymbol{b} + \frac{\epsilon}{\Omega} \left( v_1 v_\perp \frac{1}{B} \boldsymbol{n}_2(\boldsymbol{b} \cdot \nabla) \boldsymbol{B} + v_\perp^2 \frac{1}{B} \boldsymbol{n}_2(\boldsymbol{n}_1 \cdot \nabla) \boldsymbol{B} \right. \\
&+ v_1^2 \boldsymbol{b} \times [(\boldsymbol{b} \cdot \nabla) \boldsymbol{b}] + v_1 v_\perp (\boldsymbol{b} \times [(\boldsymbol{n}_1 \cdot \nabla) \boldsymbol{b}] + \boldsymbol{n}_1 \times [(\boldsymbol{b} \cdot \nabla) \boldsymbol{b}]) \\
&\left. + v_\perp^2 \boldsymbol{n}_1 \times [(\boldsymbol{n}_1 \cdot \nabla) \boldsymbol{b}] + v_1 v_\perp (\boldsymbol{n}_2 \cdot \nabla) \boldsymbol{b} \right) + \epsilon \frac{1}{B} \boldsymbol{E} \times \boldsymbol{B}.
\end{aligned}
$$
如果采用原始的形式，这个方程不但极长难以看清物理图像，且其中的运动局域坐标系依赖于相角的变化。但是平均法可以将这两个问题全部解决（前提是在小磁场梯度的情况下）。

### 导心运动（二）

引入平均导心位置：
$$
    \boldsymbol{Y}=\tilde{\boldsymbol{y}} \tag{28}
$$
对上面的运动方程右方全部取平均。略去复杂的矢量与张量计算，消去所有关于 $\boldsymbol{n}$ 的线性项，得到：
$$
\begin{aligned}
\dot{\boldsymbol{Y}} =& v_{\parallel}\boldsymbol{b} + \epsilon\frac{1}{B^2}\boldsymbol{E}\times\boldsymbol{B} + \frac{\epsilon}{\Omega}\Biggl( v_{\parallel}^2\boldsymbol{b}\times (\boldsymbol{b}\cdot \nabla\boldsymbol{b}) + v_{\perp}^2\frac{1}{B}\overline{\boldsymbol{n_2}\boldsymbol{n_1}\cdot\nabla \boldsymbol{B}} \\
&+ v_{\perp}^2\overline{\boldsymbol{n}_1\times (\boldsymbol{n}_1\cdot \nabla)\boldsymbol{b}}\Biggr) \\
=& \left( v_{\parallel} + \frac{\epsilon}{2\Omega}v_\perp^2\boldsymbol{b} \cdot (\nabla \times  \boldsymbol{b}) \right)\boldsymbol{b} + \epsilon \frac{\boldsymbol{E} \times  \boldsymbol{B}}{B^2} + \epsilon \frac{v_\perp^2}{2\Omega B}\boldsymbol{b} \times \nabla B \\
&+ \epsilon \frac{v_\parallel^2}{\Omega}\boldsymbol{b} \times  (\boldsymbol{b} \cdot \nabla)\boldsymbol{b} \qquad (29)
\end{aligned}
$$
这个方程的第一项用于描述平行运动；第二项是熟悉的电漂移，第三项是磁场梯度漂移，而第四项则是被称作离心漂移的新效应。

### 离心效应

粒子在运动中有一个绕着瞬心的运动分量，其角速度满足：
$
    \boldsymbol{v}_{\parallel}=\boldsymbol{\omega}\times \boldsymbol{\rho}=-\rho \boldsymbol{\omega}\times \boldsymbol{N}
$
那么角速度方向沿着副法线方向：
$
    \boldsymbol{\omega}=\frac{v_{\parallel}}{\rho}\boldsymbol{b}\times\boldsymbol{N}=\frac{v_{\parallel}}{\rho}\boldsymbol{\beta}
$

将旋转坐标系作为参考系，那么运动可以分为 $\boldsymbol{v}=\boldsymbol{v}_{rel}+\boldsymbol{\omega}\times\boldsymbol{\rho}$，那么 $\boldsymbol{v}_{\perp}=\boldsymbol{v}_{rel}$。
显然旋转参考系并不是惯性系，运用一些惯性力的知识可以得到：
$$
    m\boldsymbol{v}_{\perp}=\boldsymbol{f}+2m(\boldsymbol{v}_{\perp}\times \boldsymbol{\omega})-m\boldsymbol{\omega}\times (\boldsymbol{\omega}\times\boldsymbol{\rho})-m\dot{\boldsymbol{\omega}}\times \rho 
$$
其中，Coriolis 力 $2m(\boldsymbol{v}_{\perp}\times \boldsymbol{\omega})$ 平行于磁场，不产生垂直漂移；离心力
$$
    \boldsymbol{F}=-m\boldsymbol{\omega}\times (\boldsymbol{\omega}\times \boldsymbol{\rho})=-m\frac{v_{\parallel}}{\rho}\boldsymbol{N}
$$
沿着主法线方向，将会产生一个漂移。将其代入漂移运动速度的电场力则可以得到：
$$
    \boldsymbol{w}_E=\frac{1}{eB^2}(\boldsymbol{F}\times \boldsymbol{B})=\epsilon\frac{v_{\parallel}^2}{\Omega\rho }\boldsymbol{\beta} \tag{30}
$$
运用 Frenet 公式会发现这与式（29）的最后一项是相同的。

---

## 漂移近似的 Hamilton 力学体系

作者在这里介绍前人的工作（如 Kruskal）把上述的平均法纳入到 Hamilton 体系当中去。

**Kruskal‑Little John 定理**：  
存在一个从粒子精确相空间坐标 $\mathbf{z}$ 到新坐标 $\mathbf{Z}$ 的**赝正则变换**：
$$
\mathbf{z}^k = \{ \boldsymbol{q}, v_\parallel, v_\perp, \varphi \}\ (k=1,\dots,6) \quad \rightarrow \quad \mathbf{Z}^k = \{ \boldsymbol{Y}, U, W, \phi \}\ (k=1,\dots,5)
$$
该变换具有两个关键性质：

1. 新坐标的 Lie 括号不依赖于快变回旋相角（即 $\mathbf{z}^6=\varphi$）：
   $$
   [Z^k, Z^m] = \Sigma^{km}(Z^1, \ldots, Z^5)
   $$
2. 变换后的 Hamilton 函数不依赖于快变回旋相角：
   $$
   H = H(Z^1, \ldots, Z^5)
   $$

由定理直接得到运动方程的简化形式：
$$
\dot{Z}^k = [Z^k, H] = F^k(Z^1, \ldots, Z^5)
$$
变换 $\{\boldsymbol{q},v_{\parallel},v_{\perp},\varphi\}\to \{\boldsymbol{Y},U,W,\phi\}$ 为求平均赝正则变换，新变量为求平均变量，且这个变换是不唯一的。

**核心思想**：
- **完全消除快变量依赖**：运动方程右边函数 $F^k$ **不依赖于**回旋相角 $\varphi \equiv Z^6$；
- 通过精确的变换（而非近似平均）消去了对回旋相角的“可憎依赖关系”；
- 整个变换过程严格保持了理论的 Hamilton 结构。

但是没有什么实感，把它放到具体的问题中去感受一下。

---

## 漂移近似：定态均匀场

### 新变量的关于 $\epsilon$ 的幂级数展开

$$
\begin{aligned}
   &Y= \boldsymbol{q} + \epsilon \boldsymbol{\rho}(\boldsymbol{q},v_{\parallel},v_{\perp},\varphi) + O(\epsilon^{2}),\\
   &U= v_{\parallel} + \epsilon u_{\parallel}(\boldsymbol{q},v_{\parallel},v_{\perp},\varphi) + O(\epsilon^{2}),\\
   &W= v_{\perp} + \epsilon u_{\perp}(\boldsymbol{q},v_{\parallel},v_{\perp},\varphi) + O(\epsilon^{2}),\\
   &\phi= \varphi + \epsilon \psi(\boldsymbol{q},v_{\parallel},v_{\perp},\varphi) + O(\epsilon^{2}).
\end{aligned}
$$
我们要做的就是使得这些新变量的 Lie 括号不依赖于回旋相角 $\varphi$。

新的 Hamilton 量以及形式不变性：
$$
    H'(\boldsymbol{Y},U,W) = \frac{1}{2}m(U^{2}+W^{2}) - e\boldsymbol{E} \cdot \boldsymbol{Y} + O(\epsilon^{2}) \tag{31}
$$
要求 $H-H'=0$，那么可以得到：
$$
    m v_{\parallel} u_{\parallel} + m v_{\perp} u_{\perp} - e\boldsymbol{\rho} \cdot \boldsymbol{E} = 0 \tag{32}
$$

取任意一个函数 $\beta=\beta(\boldsymbol{q},v_{\parallel},v_{\perp},\varphi)$ 使得 $u_{\parallel}=v_{\perp}\beta$，
回代得到：$u_{\perp}=\frac{e}{m v_{\perp}}\boldsymbol{\rho}\cdot\boldsymbol{E} - v_{\parallel}\beta$。

因此，新变量
$$
    W = v_{\perp} - \epsilon v_{\parallel}\beta + \epsilon\frac{e}{m v_{\perp}}\boldsymbol{\rho}\cdot\boldsymbol{E} \tag{33}
$$
求下列新变量的 Lie 括号：$\{\boldsymbol{Y},W\}$。略去复杂的计算过程，注意计算中忽略 $\epsilon^2$ 小量，并注意从 $\epsilon^{-1}$ 量级到 $1$ 量级的变化，得到：
$$
    \{\boldsymbol{Y},W\} = \frac{1}{m}\boldsymbol{n_1} + \frac{\Omega}{m v_{\perp}}\frac{\partial \boldsymbol{\rho}}{\partial \varphi} + \boldsymbol{O}(\epsilon) \tag{34}
$$
我们的目的是消除振荡项 $\boldsymbol{n_1}(\varphi)$，故取其补偿：
$$
    \frac{\partial \boldsymbol{\rho}}{\partial \varphi} = -\frac{v_{\perp}}{\Omega}\boldsymbol{n_1}
$$
再由之前的局域运动坐标系关系可得：
$$
    \boldsymbol{\rho} = -\frac{v_{\perp}}{\Omega}\boldsymbol{n_2} \tag{35}
$$

另一个比较麻烦的是 $\{W,\phi\}$，作者也顺手写了一下，这里仅展示结果：
$$
    \{W,\phi\} = - \frac{1}{\epsilon} \frac{\Omega}{m v_{\perp}} + \frac{\Omega}{m v_{\perp}} \left( v_{\parallel} \frac{\partial \beta}{\partial v_{\perp}} - \frac{\partial \psi}{\partial \varphi} \right).
$$
将式 (31) 与 (33) 代入得到：
$$
    \{W,\phi\} = - \frac{1}{\epsilon} \frac{\Omega}{m W} + \frac{\Omega}{m v_{\perp}} \left( \frac{v_{\parallel}}{v_{\perp}} \beta + v_{\parallel} \frac{\partial \beta}{\partial v_{\perp}} + \frac{e}{m \Omega v_{\perp}}\boldsymbol{E} \cdot \boldsymbol{n}_{2}(\varphi) - \frac{\partial \psi}{\partial \varphi} \right) \tag{36}
$$
这里有一个小问题，教材上这个式子尾部是 $\frac{\partial \psi}{\partial \rho}$，不知是否是印刷错误。

由于 $\beta$ 的任意性，取 $\beta = 0$，再令 $\frac{\partial \psi}{\partial \varphi} = \frac{e}{m \Omega v_{\perp}}\boldsymbol{E} \cdot \boldsymbol{n}_{2}(\varphi)$，即 $\psi = -\frac{e}{m\Omega v_{\perp}}\boldsymbol{E}\cdot\boldsymbol{n_1}$。消除振荡项从而得到
$$
    \{W,\phi\} = -\frac{1}{\epsilon}\frac{\Omega}{m v_{\perp}} \tag{37}
$$

### 新旧变量变换关系

$$
\begin{aligned}
   &\boldsymbol{Y} = \boldsymbol{q} - \epsilon \frac{v_{\perp}}{\Omega}\boldsymbol{n}_{2}(\varphi) + O(\epsilon^{2}),\\
   &U = v_{\parallel} + O(\epsilon^{2}),\\
   &W = v_{\perp} - \epsilon \frac{e}{m \Omega}\boldsymbol{E} \cdot \boldsymbol{n}_{2}(\varphi) + O(\epsilon^{2}),\\
   &\phi = \varphi - \epsilon \frac{e}{m \Omega v_{1}}\boldsymbol{E} \cdot \boldsymbol{n}_{1}(\varphi) + O(\epsilon^{2}).
\end{aligned} \tag{38}
$$

### Lie 括号

$$
\begin{aligned}
   &\{Y_i,Y_j\} = -\epsilon\frac{1}{eB}\epsilon_{ijk}\boldsymbol{b},\\
   &\{\boldsymbol{Y},U\} = \frac{1}{m}\boldsymbol{b},\quad \{U,W\}=0,\\
   &\{U,\phi\}=0,\quad \{W,\phi \} = \frac{1}{\epsilon}\frac{\Omega}{m v_{\perp}},\\
   &\{\boldsymbol{Y},W\}=0,\quad \{\boldsymbol{Y},\phi\}=0.
\end{aligned} \tag{39}
$$
这些结果都摆脱了振荡项中的回旋相角的影响。

运用 Hamilton 函数可以得到运动方程如下：
$$
    \begin{array}{c}
       \dot{\boldsymbol{Y}} = U\boldsymbol{b} + \epsilon\frac{\boldsymbol{E}\times \boldsymbol{B}}{B^{2}},\\
       \dot{U} = \frac{e}{m}\boldsymbol{E}\cdot\boldsymbol{B},\\
       \dot{W} = 0,\\
       \dot{\phi} = \frac{1}{\epsilon}\Omega.
    \end{array} \tag{40}
$$
可以看到这里面每个式子的物理意义都是很清晰的。

---

## 漂移近似：定态不均匀场

在这里，其基本思想是一致的：对新变量进行量级 $\epsilon$ 的级数展开，用类似的方法求平均赝正则变换，可以验证其括号运算不依赖于振荡项。只不过，由于涉及不均匀场，其磁场实际上写作：
$$
    \boldsymbol{B}(x)=B(x)\boldsymbol{b}(x)
$$
这意味着不仅磁场本身大小会发生变化，方向也在一同改变。也正因为如此，其具体形式是极为复杂的。书中给出了 Lie 括号和运动方程的结果（图片已略去），但这一章节最重要的部分是有关自然导心变量的内容。

### 定态不均匀场中的导心变量

**变换非唯一性**：  
在获得一组求平均变量 $Z^k = (Y, U, W, \phi)$ 后，存在无穷多组满足条件的变量。其中，具有清晰物理意义的称为**导心变量**。  
任何形如 $(Y, P_1, P_2, \phi)$ 的变量集合，其中 $Y$ 为导心坐标，$(P_1, P_2)$ 替换 $(U, W)$，均称为**导心变量**。

**自然导心变量 (NGC)**：  
在导心变量中，满足以下特殊条件的子集：
$$
H' = H + O(\epsilon^2)
$$
即，用新变量表达的 Hamilton 函数不包含量级为 $\epsilon$ 的修正项。这类变量称为**自然导心变量**。

### 定态不均匀场的核心运动不变量

**绝对不变量：总能量**
$$
\mathcal{E} = \frac{1}{2}m(U^2 + W^2) + e\Phi(Y)
$$
该量在精确运动方程下严格守恒：
$$
[\mathcal{E}, H] = 0
$$

**浸渐不变量：磁矩**
$$
M = \frac{m}{2}\frac{W^2}{B(Y)}
$$
其变化率：
$$
\dot{ M} = m \frac{v_{\perp}}{B} \left(-v_{\parallel}\boldsymbol{n}_{2} \cdot \boldsymbol{D} - \frac{e}{m}\boldsymbol{n}_{1} \cdot \nabla \Phi \right) - \frac{m}{2} \frac{v_{\perp}^{2}}{B^{2}} \left( v_{\parallel}\boldsymbol{b}+v_{\perp}\boldsymbol{n}_{1} \right) \cdot \nabla \boldsymbol{B}.
$$
该量在均匀磁场中严格守恒，在缓变场中近似守恒：
$$
\dot{M} = 0 + O(\epsilon^2)
$$

**磁矩不变量的性质**：
- 与垂直速度的关系：
  $$
  W = +\sqrt{\frac{2}{m}B(Y)M}
  $$
  符号必须为正，以保证 $\epsilon \to 0$ 时连续趋于 $v_\perp$。
- 不变性级别：能量 $\mathcal{E}$ 是**绝对不变量**（精确守恒），磁矩 $M$ 是**浸渐不变量**（近似守恒）。Kruskal 从数学上证明了磁矩不变量可扩展至任意阶 $\epsilon$，但显式形式通常只求至 $\epsilon^2$ 量级。

### 自然导心变量组合

在新经典输运理论中，有一个动能的定义十分重要。基于能量 $\mathcal{E}$ 和磁矩 $M$，定义动能：
$$
K = \mathcal{E} - e\Phi(Y) \tag{41}
$$

实践中特别有用的 NGC 变量组合：
1. $(Y, U, M, \phi)$ —— 包含平行速度；
2. $(Y, \mathcal{E}, M, \phi)$ —— 包含总能量；
3. $(Y, K, M, \phi)$ —— 包含动能（在新经典输运理论中尤其有用）。

这些变量的具体性质通常以表格形式总结，这里不展示了。

---

## 漂移近似：随时间慢变不均匀场

### 非自治 Hamilton 体系

这一节的核心思想在于将时间 $t$ 作为一个动力学函数纳入到 Hamilton 体系中，从而确立体系与时间的依赖关系。

- 将时间 $t$ 视为新的**动力学变量**；
- 引入其共轭动量 $h$（物理上对应总能量）；
- 相空间扩展为 8 维：$(\mathbf{q}, t; \mathbf{p}, h)$。

数学上将这些变量视为独立，通过引入抽象固有时 $\tau$ 来参数化运动。

### 扩展相空间的代数结构

**基本 Lie 括号定义**：在标准正则括号基础上，增加时间 $t$ 和能量 $h$ 的括号：
$$
\begin{aligned}
   &[q_i, q_j] = 0,\quad [p_i, p_j] = 0,\quad [q_i, p_j] = \delta_{ij},\\
   &[t, q_i] = 0,\quad [t, p_i] = 0,\quad [h, q_i] = 0,\\
   &[h, p_i] = 0,\quad [t, h] = 1.
\end{aligned}
$$

**扩展 Hamilton 函数**：
$$
    \tilde{H}(\mathbf{q}, \mathbf{p}, t, h) \equiv H + h = \frac{1}{2m}\left|\mathbf{p} - \frac{e}{c}\mathbf{A}(\mathbf{q}, t)\right|^2 + e\Phi(\mathbf{q}, t) + h \tag{42}
$$

**运动方程**：
$$
    \dot{a} = \frac{da}{d\tau} = [a, \tilde{H}], \quad \text{其中 } a \text{ 是 } \mathbf{q}, \mathbf{p}, t, h \text{ 的任意函数} \tag{43}
$$

### 速度变量下的理论框架

**变量变换**：从正则动量 $\mathbf{p}$ 变换到物理速度 $\mathbf{v}$：
$$
(\mathbf{q}, \mathbf{p}, t, h) \rightarrow (\mathbf{q}, \mathbf{v}, t, h)
$$
扩展的 Lie 括号需要重新计算，特别是 $[\mathbf{v}, h]$ 项包含了时间导数 $\partial_t \mathbf{A}$。

**变换后的 Hamilton 函数**：
$$
    \tilde{H}(\mathbf{q}, \mathbf{v}, t, h) = \frac{1}{2}m\mathbf{v}^2 + e\Phi(\mathbf{q}, t) + h \tag{44}
$$

运动方程的物理意义：
- 位置和速度方程与自治情况形式相同；
- 新增方程：$\dot{h} = \frac{e}{c}\mathbf{v}\cdot\partial_t\mathbf{A} - e\partial_t\Phi$。

### 标度分析与物理近似

为保持数学一致性，引入小参数 $\epsilon$：
$$
\begin{aligned}
   &c \rightarrow \frac{1}{\epsilon}c,\quad B \rightarrow \epsilon^0 B,\\
   &\Phi \rightarrow \epsilon\Phi,\\
   &\partial_t \mathbf{A} \rightarrow \epsilon^2\partial_t\mathbf{A},\quad \partial_t\mathbf{b} \rightarrow \epsilon^2\partial_t\mathbf{b},\\
   &\partial_t\Phi \rightarrow \epsilon^3\partial_t\Phi.
\end{aligned}
$$

扩展的 Kruskal‑Littlejohn 定理：存在从粒子变量 $z^\lambda$ 到新变量 $Z^\lambda$ 的赝正则变换，使得：
- 所有基本 Lie 括号 $[Z^\lambda, Z^\mu]$ 不依赖于回旋相角 $\phi \equiv Z^6$；
- 变换适用于 8 维扩展相空间 $(\mathbf{q}, \mathbf{v}, t, h)$。

### 自然导心变量的显式构造

- 导心位置：$\mathbf{Y} = \mathbf{q} - \frac{\epsilon}{\Omega}v_\perp\mathbf{n}_2$；
- 能量：$\mathcal{E} = \frac{1}{2}m(v_\parallel^2 + v_\perp^2) + e\Phi$；
- 磁矩：$M = \frac{m}{2B}v_\perp^2 + \frac{\epsilon}{\Omega B}[\cdots]$；
- 回旋相角：$\phi = \varphi + \frac{\epsilon}{\Omega}[\cdots]$；
- 扩展变量：$k = h,\quad t' = t$。

**简化结果**：
- 扩展 Hamilton 函数：$\tilde{H} = \mathcal{E} + k$（极其简洁！）；
- 磁矩 $M$ 仍是浸渐不变量；
- 能量 $\mathcal{E}$ 不再严格守恒（反映时变场中的能量交换）。

这样我们将单个粒子在依赖时间的慢变不均匀场的运动纳入了 Hamilton 体系。