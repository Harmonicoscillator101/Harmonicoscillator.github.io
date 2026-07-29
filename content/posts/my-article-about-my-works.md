---
date: '2026-07-28T20:34:48+08:00'
draft: false
title: '我当前正在进行的工作'
math: true
tags: ["等离子体", "输运理论"]
categories: ["物理学"]
---
# 等离子体输运理论

等离子输运理论是等离子体动理学的一个部分，归根结底在于想办法用更高效的方法构建玻尔兹曼方程与模拟计算之间的桥梁。玻尔兹曼方程定义为：
$$\partial_t f_a + \mathbf{v} \cdot \nabla f_a + \frac{e_a}{m_a}(\mathbf{E} + \mathbf{v} \times \mathbf{B}) \cdot \partial_{\mathbf{v}} f_a = \sum_b C(f_a, f_b)$$
其中$f_a$是物种$a$粒子的分布函数，而$C(f_a,f_b)$则是碰撞项。等离子体输运理论最终都在关注这个碰撞项的截断。现在我主要精力在于关注Jeong-Young Ji and Eric D. Held在[2006年发表在POP上的工作](/files/jijy06.pdf)并学习其推导高阶矩的一般方法，如我的[文献阅读工作1](/files/5.31：Ji论文复推.pdf)和[文献阅读工作2](/files/6.7：Ji论文复推2.pdf)