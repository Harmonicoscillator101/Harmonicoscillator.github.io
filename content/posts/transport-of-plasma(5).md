---
title: "等离子体输运理论(5)"
date: 2026-08-03
draft: false
math: true
tags: ["等离子体", "输运理论","笔记"]
categories: ["物理"]
---
# 等离体动理方程

## 相互作用带电粒子系统

### 含相互作用势的 Hamilton 量

最为简单的方法是为 Hamilton 函数添加相互作用势，如下所示：

含相互作用势的 Hamilton 函数：


\begin{aligned}
H(q,v) &= \sum_{j=1}^N \left[ \frac{1}{2} m_{a_j} v_j^2 + e_{a_j} \Phi_0(q_j) \right] + \sum_{n=1}^N \sum_{j=1}^{j<n} V_{j,n}(q_j,q_n)= \sum_{j=1}^N H_{0_j}^a + \sum_{n=1}^N \sum_{j=1}^{j<n} V_{j,n}
\end{aligned}


带电粒子系统中两个粒子首先满足库仑定律，因此势函数可以写为：
$$
V_{j,n}(q_j,q_n) = e_{a_j} e_{a_n} \frac{1}{|\boldsymbol{q} - \boldsymbol{q}_n|}
$$
因此势函数仅仅依赖于粒子之间的距离。

### 全电离非相对论等离体模型

以上的式子满足两个近似：

1. 粒子系统是全电离的，排除了中性粒子，以及电荷交换等其他的相互作用，总之粒子系统是相当理想的。
2. 粒子系统必须符合非相对论近似，换言之它们的相对速度没有达到光速量级以至于相对论效应可以忽略。

太多复杂的细枝末节先不考虑，这样构成了全电离非相对论等离体模型。

### 含相互作用的约化分布函数

从多粒子相空间分布函数 $F(q, v; t)$ 出发，服从 Liouville 方程，其中 Hamilton 函数 $H$ 包含粒子间相互作用项。

约化分布函数方程：引入约化单粒子分布函数 $f^a(q_1, v_1; t)$，从 Liouville 方程导出：
$$
\partial_t f^a(q_1, v_1; t) = L_1^a f^a + \sum_{\beta} \int dq_2 dv_2 \, L_{12}^{a\beta} f^{a\beta}
$$
其中 $L_{12}^{a\beta} G = [V_{12}^{a\beta}, G]$ 为相互作用 Liouville 算符。

单粒子方程中出现了双粒子分布函数 $f^{a\beta}(q_1, v_1, q_2, v_2; t)$。若进一步推导双粒子方程，则会出现三粒子分布函数，形成耦合的无穷层级：
$$
\partial_t f^a \rightarrow f^{a\beta} \rightarrow f^{a\beta\gamma} \rightarrow \cdots
$$
这正是 BBGKY 级列方程，反映了统计力学中的根本困难。

### 二体关联函数与弱耦合近似

二体关联函数的定义：引入二体关联函数描述系统偏离概率密度相互独立的程度：
$$
g^{\alpha\beta}(q_1,v_1,q_2,v_2;t) = f^{\alpha\beta} - f^\alpha f^\beta
$$

物理性质：
- 关联长度 $r_c$：当 $|q_1-q_2| > r_c$ 时，$g^{\alpha\beta} \approx 0$
- 归一化性质：$\int dq_1 dv_1 dq_2 dv_2\, g^{\alpha\beta} = 0$

类似地可以定义三体、四体关联函数，从而表征粒子相互之间的影响程度。

### Debye 长度与等离体参数

介绍等离体参数的过程中用到了 Debye 长度，这来源于 Debye 屏蔽。

**Debye 屏蔽**：在等离子体中，任何一个带电粒子总是被周围的异性粒子所包围，在超出一定的距离后，该粒子的电场作用就几乎消失，实际上就是被周围的异性粒子所屏蔽了。这个距离就是 Debye 长度。

**Debye 长度**：Debye 长度一般是根据泊松方程解出来的，具有如下的形式：
$$
\lambda_D = \sqrt{\frac{\epsilon_0 K T_e}{n e^2}}
$$
其中 $n$ 为粒子密度，$KT$ 为粒子热能，本书中写为：
$$
\lambda_D = \left( \frac{4\pi Ze^2 (n_e T_e + n_1 T_1)}{T_e T_1 (1+Z)} \right)^{-\frac{1}{2}}
$$

**等离体参数**：定义无量纲数 $\mu_p$：
$$
\mu_p = \left( \frac{4}{3}\pi \lambda_D n_1 \right)^{-\frac{2}{3}}
$$
这可以看作是相互作用能与热能之比。由于等离体是弱耦合的，所以
$$
\mu_D \ll 1
$$
这意味着在低密度或者高温度下满足理想条件。

因此在弱耦合条件下，相互作用能与平均动能相比非常小，因此前面定义的关联函数 $g^{\alpha\beta}$ 也非常小，与相互作用能是相同量级，多体关联函数则是高阶小量。

### 弱耦合近似下的 BBGKY 层级截断

截断后的耦合方程：忽略三体及以上关联，得到两个方程：

- **单粒子方程**：
$$
\partial_t f^\alpha = L_1^\alpha f^\alpha + \sum_\beta \int d2\, L_{12}^{\alpha\beta} [ f^\alpha f^\beta + g^{\alpha\beta} ]
$$

- **二体关联方程**：复杂方程，包含三体相互作用项，不列出。

### 两种简化形式及其物理意义

**简化形式 [BL]：Balescu-Lenard 方程**  
保留与第三粒子的相互作用：
$$
\partial_t g^{\alpha\beta} - (L_1^\alpha + L_2^\beta)g^{\alpha\beta} = \sum_\gamma \int d3\,
\left[
L_{13}^{\alpha\gamma} f^\alpha g^{\beta\gamma} + L_{23}^{\beta\gamma} f^\beta g^{\alpha\gamma}
\right] + L_{12}^{\alpha\beta} f^\alpha f^\beta
$$
描述多体相互作用和集体效应。

**简化形式 [L]：Landau 方程**  
仅考虑两体碰撞驱动：
$$
\partial_t g^{\alpha\beta} - (L_1^\alpha + L_2^\beta)g^{\alpha\beta} = L_{12}^{\alpha\beta} f^\alpha f^\beta
$$
描述纯两体碰撞演化，忽略集体效应。

### 从关联方程到动理方程

**目标：消去关联函数**

单粒子方程包含关联函数 $g^{\alpha\beta}$：
$$
\partial_t f^\alpha = L_1^\alpha f^\alpha + \sum_\beta \int d2\, L_{12}^{\alpha\beta} \left[ f^\alpha f^\beta + g^{\alpha\beta} \right]
$$
需将 $g^{\alpha\beta}$ 表示为 $f$ 的函数，得到封闭方程。

**动理区假设**：在动理演化阶段，关联函数成为单粒子分布函数的瞬时泛函：
$$
g^{\alpha\beta}(t) = g^{\alpha\beta}[f(t)]
$$
即关联函数由同一时刻的单粒子分布函数完全决定。

### 封闭的动理方程

将泛函关系代入单粒子方程，得到：

$$
\partial_t f^\alpha(1;t) = L_1^\alpha f^\alpha(1;t) + \sum_\beta \int d2\, L_{12}^{\alpha\beta} f^\alpha f^\beta + \mathcal{K}^\alpha[f(t)]
$$

其中 $\mathcal{K}^\alpha[f(t)]$ 为碰撞项，来源于关联函数 $g^{\alpha\beta}[f]$ 的贡献。

这样得到了动理方程的一般形式，表征一个单粒子含时分布函数一个闭合、非线性的演化方程。可以注意到在引入线性泛函后，Liouville 结构就已然消失了。

---

## Vlasov 动理方程

### 动理方程的明确形式：平均场项

相互作用 Liouville 算符：
$$
L_{12}^{\alpha\beta} = [\nabla_1 V^{\alpha\beta}(q_1-q_2)] \cdot (\partial_1 - \partial_2)
= e_\alpha e_\beta \left( \nabla_1 \frac{1}{|q_1-q_2|} \right) \cdot (\partial_1 - \partial_2)
$$
其中 $\nabla_1 \equiv \partial/\partial q_1$，$\partial_1 \equiv \partial/\partial v_1$。

**平均场项推导**：
$$
\begin{aligned}
\sum_\beta & \int d2\, L_{12}^{\alpha\beta} f^\alpha(1;t)f^\beta(2;t) \\
&= \left( \nabla_1 \sum_\beta \int d2\, V_{12}^{\alpha\beta} f^\beta(2;t) \right) \cdot \frac{1}{m_\alpha} \partial_1 f^\alpha(1;t) \\
&\equiv -\frac{e_\alpha}{m_\alpha} \bar{E}(q_1;t) \cdot \partial_1 f^\alpha(1;t)
\end{aligned}
$$

### 平均电场的物理意义

平均电场定义：
$$
\bar{E}(q_1;t) = -\nabla_1\bar{\Phi}(q_1;t)
$$
$$
\bar{\Phi}(q_1;t) = \sum_\beta e_\beta \int dq_2 dv_2 \frac{1}{|q_1-q_2|} f^\beta(q_2,v_2;t)
$$

**物理解释**：平均势 $\bar{\Phi}$ 由宏观电荷分布 $\sigma(q;t)$ 产生，满足泊松方程：

Poisson 方程：
$$
\nabla^2 \bar{\Phi}(q;t) = -4\pi\sigma(q;t), \qquad 
\sigma(q;t) = \sum_\beta e_\beta \int dv\, f^\beta(q,v;t)
$$
平均电场 $E_0$ 由外部源产生，满足 Laplace 方程（$\sigma=0$）。

### 总电场与 Vlasov 方程

总电场为外场与平均场之和：
$$
E(q;t) = E_0(q;t) + \bar{E}(q;t)
$$
对应势 $\Phi = \Phi_0 + \bar{\Phi}$ 满足带源项的 Poisson 方程。

忽略碰撞项 $\mathcal{K}^\alpha$，动理方程化为：

**Vlasov 方程**：
$$
\partial_t f^\alpha(1;t) = -v_1\cdot\nabla_1 f^\alpha - \frac{e_\alpha}{m_\alpha}
\left((v_1\times B) + E \right) \cdot \partial_1 f^\alpha
$$
这与 Liouville 方程的第一种形式很像，但是注意此处的电场应当满足 Poisson 方程，因此不具有 Liouville 方程那样的线性性，反而会带来湍流。

### 与麦克斯韦方程组结合

在这里面，$E$ 是总场，而 $B$ 纯粹是外场，比较完全的处理应当包括电磁相互作用。对磁场做一个简单的处理：粒子的平均运动成为引起内磁场 $B(q,t)$ 的源，将其与外磁场相加从而得到总磁场。

**完整 Maxwell 方程组**：
$$
\begin{aligned}
\nabla\cdot E(q;t) &= 4\pi \sum_\beta e_\beta \int dv\, f^\beta(q,v;t) \\
\nabla\times E(q;t) &= -c^{-1} \partial_t B(q;t) \\
\nabla\cdot B(q;t) &= 0 \\
\nabla\times B(q;t) &= c^{-1} \partial_t E(q;t) + \frac{4\pi}{c} \sum_\beta e_\beta \int dv\, v\, f^\beta(q,v;t)
\end{aligned}
$$