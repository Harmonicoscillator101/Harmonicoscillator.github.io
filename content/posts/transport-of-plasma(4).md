---
title: "等离子体输运理论(4)"
date: 2026-08-01
draft: false
math: true
tags: ["等离子体", "输运理论","笔记"]
categories: ["物理"]
---
# 等离体分布函数的导出与微观机制

## 相空间分布函数

### 相空间分布函数

相空间分布函数 $F(q,p;t)$ 满足归一化条件：
$$
\int F(q,p;t)d^{3N}qd^{3N}p = 1
$$
可以将 $F$ 看作 $t$ 时刻 $(q,p)$ 的概率密度。

相空间的概率密度自然满足 Liouville 定理：

**Liouville 定理**：
$$
\frac{dF}{dt} = \frac{\partial F}{\partial t} + \{F, H\} = 0
$$
记 $L$ 为 Liouville 算符：
$$
\frac{\partial F}{\partial t} = \{H, F\} = LF, \qquad L = -\sum_j \left( \dot{\boldsymbol{q}}_j \frac{\partial}{\partial q_j} + \dot{\boldsymbol{p}}_j \frac{\partial}{\partial p_j} \right)
$$

### 约化分布函数

将分布函数简化为约化分布函数以考虑最重要的关系。

**约化分布函数 $\hat{f_s^a}(q_1,\dots,q_s,p_1,\dots,p_s;t)$**：

对于单粒子（$a$ 表示粒子种类，$N_a$ 为该种粒子的数量）：
$$
\hat{f}^a_1(q_1,p_1;t) = N_a \int F(q,p;t) \, dq_2 \cdots dq_N \, dp_2 \cdots dp_N
$$
满足归一化条件：
$$
\int \hat{f}^a(q,p;t) \, dp_1 \, dq_1 = N_a
$$

动力学函数 $b$ 的加权平均值：
$$
\langle b \rangle = \sum_a \int b^a(q,p) \, \hat{f}^a_1(q,p;t) \, dq \, dp
$$


## 定态场中独立单粒子系统

### Liouville 方程

主要目标是导出 $\hat{f}^a_1(q,p;t)$ 的封闭演化方程。考虑定态外加电磁场，且粒子系统是理想系统，即粒子之间没有相互作用，且粒子种类相同。这些粒子总共的 Hamilton 函数为：
$$
H(q,p) = \sum_{j=1}^N \left( \frac{1}{2m_{a_j}} |\boldsymbol{p}_j - e_a \boldsymbol{A}(\boldsymbol{q}_j)|^2 + e_a \Phi_0(\boldsymbol{q}_j) \right) = \sum_j H_j^a(q_j,p_j)
$$

求和 Liouville 算符：
$$
L = \sum_j L_j^a
$$
$$
L_j^a = -\left( \{q_j, H_j\} \frac{\partial}{\partial q_j} + \{p_j, H_j\} \frac{\partial}{\partial p_j} \right)
$$
$$
\frac{\partial F}{\partial t} = LF = \left( \sum_j^N L_j^a \right) F
$$

### Liouville 方程第一种形式

两边乘上 $N_a$ 再对无约束关系的粒子位置与动量求积分：
$$
\int N_a \frac{\partial F}{\partial t} \, dp_2 \cdots dp_N \, dq_2 \cdots dq_N = \int N_a \left( \sum_j^N L_j^a \right) F \, dp_2 \cdots dp_N \, dq_2 \cdots dq_N
$$
从而得到 Liouville 方程的第一种情况：

**Liouville 方程的第一种形式**：
$$
\frac{\partial}{\partial t} \hat{f}^a = L^a \hat{f}^a(q,p,t) = \{H^a, \hat{f}^a\} = \{H_0^a, q\} \frac{\partial \hat{f}^a}{\partial q} + \{H_0^a, p\} \frac{\partial \hat{f}^a}{\partial p}
$$
其中
$$
H_0^a = \frac{1}{2m_a} |\boldsymbol{p} - e_a \boldsymbol{A}(\boldsymbol{q})|^2 + e_a \Phi_0(\boldsymbol{q})
$$

### 赝正则变换

$(q,p)$ 在物理学中是不便的，要将其变换成 $(q,v)$ 或者导心运动变量等。

**相空间坐标变换**：
$$
\hat{f}^a(q,p;t) \to \hat{f}'^a(Q,P;t)
$$
$$
b^a(q,p) \to b'^a(Q,P)
$$
动力学函数平均值：
$$
\langle b \rangle = \sum_a \int d\boldsymbol{Q} \, d\boldsymbol{P} \, |J^a(\boldsymbol{Q}, \boldsymbol{P})| \, b'^a(\boldsymbol{Q}, \boldsymbol{P}) \, \hat{f}'^a(\boldsymbol{Q}, \boldsymbol{P}; t)
$$
在这里面出现了 Jacobi 行列式，这是由于变换为真实分布函数：
$$
\hat{f}^a(q,p;t) = |J^a(Q,P)| \, \hat{f}'^a(Q,P;t)
$$
且仍要满足归一化条件：
$$
\int dQ \, dP \, |J^a(Q,P)| \, \hat{f}'^a(Q,P;t) = N_a
$$

### Liouville 方程第二种形式

**一个重要引理**：
$$
\sum_{i=1}^{f} \left( \frac{\partial}{\partial Q_i} \left( |J^a| \, \{H, Q_i\} \right) + \frac{\partial}{\partial P_i} \left( |J^a| \, \{H, P_i\} \right) \right) = 0
$$

将其与 Liouville 定理结合，就得到了真实分布函数的演化方程：

**Liouville 方程的第二种形式**：
$$
\frac{\partial}{\partial t} |J^a| \hat{f}'^a = \frac{\partial}{\partial Q} \cdot \left( [H_0^a, Q] \, |J^a| \hat{f}^a \right) + \frac{\partial}{\partial P} \cdot \left( [H_0^a, P] \, |J^a| \hat{f}^a \right)
$$

### 将广义动量变换为机械动量

将广义动量 $p$ 替换为机械动量 $mv$，从而有以下的变换：
$$
\hat{f}^a(\boldsymbol{q}, \boldsymbol{p};t) \to |J^a| \hat{f}'^a(\boldsymbol{q}, \boldsymbol{v};t), \qquad |J^a| = m_a^3
$$
再定义 $f^a(q,v;t) = |J^a| \hat{f}'^a(q,v;t)$，且仍满足归一化条件。之后都以 $(q,v) \to (Q,P)$ 做非正则变换。

**机械动量的 Liouville 算符**：
$$
\frac{\partial}{\partial t} f^a = L^a f^a(\boldsymbol{q}, \boldsymbol{v};t)
$$
将算符替换为：
$$
\mathscr{L}^a = -\frac{\partial}{\partial \boldsymbol{q}} \cdot \boldsymbol{v} - \frac{\partial}{\partial \boldsymbol{v}} \cdot \frac{e_a}{m_a} \left[ \boldsymbol{v} \times \boldsymbol{B}(\boldsymbol{q}) + \boldsymbol{E}(\boldsymbol{q}) \right]
$$
故第二种形式为：
$$
\frac{\partial}{\partial t} |J^a| f^a = \mathscr{L}^a |J^a| f^a
$$


## 时变外场独立单粒子系统

### 扩展相空间中的统计力学表述

在随时间变化外场中，传统相空间需要扩展：

- 添加正则变量对：$t$（时间）和 $h$（共轭变量）
- 扩展 Hamilton 函数：$H(q,p,t,h) = H_0(q,p,t) + h$
- 使用固有时 $\tau$ 参数化运动

扩展相空间中的归一化条件：
$$
\int dQ \, dP \int dk \int dt \, |\tilde{J}^a(Q,P,k,t)| \, \tilde{f}^a(Q,P,k,t;\tau) = N_a
$$
这要求对时间 $t$ 从 $-\infty$ 到 $+\infty$ 积分，涉及整个系统历史，物理上不合理。

**核心问题**：数学上独立的变量 $(Q,P,k,t)$ 在物理上并不独立，需要通过约束条件来限制积分区域。

### 弱方程与物理约束

**弱方程**：
- **时间约束**：$t = \tau$
- **能量约束**：$\dot{H}_0^a(Q,P,t) = -\dot{k}$，等价于 $H_0^a(Q,P,k,t) = H_0^a(Q,P,t) + k = 0$

Dirac 的弱方程理论：
- 在计算 Poisson 括号前，不能使用约束条件
- 约束条件只能作为“弱方程”使用

**新的归一化条件**：使用 Dirac delta 函数限制到物理可及区域：
$$
\int dQ \, dP \int dk \int dt \, |J^a| \, \delta(\tilde{H}^a) \, \delta(t-\tau) \, \tilde{f}^a(Q,P,k,t) = N_a
$$
其中 $\delta(\tilde{H}^a)$ 实施能量约束，$\delta(t-\tau)$ 实施时间约束。

### 含时的 Liouville 方程

对 $t$ 作平凡积分将其消去，再引入物理分布函数：
$$
f^a(Q,P;t) = \int dk \, \delta(\tilde{H}_0^a(Q,P;t) + k) \, \tilde{f}^a(Q,P,k,t;t)
$$
这一个分布函数也满足归一化条件。

**含时 Liouville 方程**：
$$
\begin{aligned}
&\frac{\partial}{\partial t} |J^a(Q,P,t)| f^a(Q,P;t) \\
&= \left( \frac{\partial}{\partial Q} \cdot [H_0^a(Q,P,t), Q] + \frac{\partial}{\partial P} \cdot [H_0^a(Q,P,t), P] \right) \\
&\quad \times |J^a(Q,P,t)| f^a(Q,P;t)
\end{aligned}
$$
或者更简洁地写为：
$$
\frac{\partial}{\partial t} |J^a| f^a(t) = \mathscr{L}^a |J^a| f^a(t)
$$