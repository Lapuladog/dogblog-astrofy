---
title: "对数正态分布"
description: "对数正态分布"
pubDate: "Sep 10 2022"
heroImage: "/post_img.webp"
tags: ["Math"]
---

# 对数正态分布

> Logarithmic Normal Distribution



## 前提知识

### 随机变量的无条件期望

$$
\mathbb{E}(x)=\int_{-\infty}^{\infty}xf(x)dx
$$

### 随机变量的部分期望 

> partial expectation

$$
g(\bar{x})=\int_{-\infty}^{\bar{x}}xf_X(x|X<\bar{x})dx=\mathbb{E}[x|x\leq\bar{x}]P(x\leq\bar{x})=\mathbb{E}[x|x\leq\bar{x}]F(\bar{x})\\
\mathbb{E}[x|x\leq\bar{x}] = g(\bar{x})F(\bar{x})^{-1}
$$


注：差别在于，是否将整个定义域作为概率空间：如果在整个概率空间内考虑期望就是 $g(\bar{x})$，即认为整个概率空间的测度为1；如果在局部空间内考虑期望就是 $\mathbb{E}[x|x\leq\bar{x}]$，即认定局部概率空间的测度为1



## 对数正态分布

设 $w$ 为随机变量，对数正态分布为：

$$
\ln \omega \sim N(\mu,\sigma^2)
$$

### 累积分布

$$
F(\omega)=\Phi\left(\frac{\ln\omega-\mu}{\sigma}\right)
$$

### 概率密度

$$
f(\omega)=F'(\omega)=\phi\left(\frac{\ln\omega-\mu}\sigma\right)\frac1{\omega\sigma}
$$

其中，
$$
\phi(\cdot)=\Phi'(\cdot)
$$

### 概率密度函数（拓展）

$$
f(\omega)=\frac1\omega\frac1{\sigma\sqrt{2\pi}}\exp\left(-\frac{(\ln\omega-\mu)^2}{2\sigma^2}\right)
$$



## 对数正态分布的基本性质

### 无条件期望

$$
\mathbb{E}[\omega]=\exp\left(\mu+\frac1{2}\sigma^2\right)
$$

特别的，当 $\mathbb{E}[\omega]=1$ 时
$$
\mu = -\frac1{2}\sigma^2
$$

### 部分期望

基于 $\omega \le \bar{\omega}$ 条件期望
$$
g(\bar{\omega})=\mathbb{E}[\omega|\omega\leq\bar{\omega}]P(\omega<\bar{\omega})
=\int_{0}^{\bar{\omega}}\omega f(\omega)d\omega 
=\int_{0}^{\bar{\omega}}\omega dF(\omega) 
$$
特别的，当 $\mathbb{E}[\omega]=1$ 时
$$
g(\bar{\omega})=
\int_{0}^{\bar{\omega}}\omega f(\omega)d\omega =\Phi\left(\frac{\ln\bar{\omega}-\mu-\sigma^2}\sigma\right)\\[1em]
1-g(\bar{\omega})
=\int_{\bar{\omega}}^{\infty}\omega f(\omega)d\omega 
=\Phi\left(\frac{\mu+\sigma^2-\ln\bar{\omega}}\sigma\right)
$$


## 部分期望微分

### 莱布尼茨公式

$$
\frac{d}{dx}\left[\int_{a(x)}^{b(x)}f(x,z)dz\right]=f(x,b(x))b'(x)-f(x,a(x))a'(x)+\int_{a(x)}^{b(x)}f_x(x,z)dz
$$

### 部分期望微分

$$
\begin{aligned}
g'(\bar{\omega}) 
&= \bar{\omega}f(\bar{\omega})\frac{d\bar{\omega}}{d\bar{\omega}}-\infty f(\infty)\frac{d0}{d\bar{\omega}}+\int_{\bar{\omega}}^\infty\left(\omega f^{\prime}(\omega)+f(\omega)\right)\frac{d\omega}{d\bar{\omega}}d\omega
\\&= \bar{\omega}f(\bar{\omega})
\\[0.5em]&=\bar{\omega}F_{\omega}(\bar{\omega})
\end{aligned}
$$















