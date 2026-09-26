# 附录 A.0.3 Hölder 不等式及其应用

Hölder 不等式是泛函分析中的核心不等式，在函数空间理论和偏微分方程中具有广泛应用。作为其基础，我们首先回顾 **Young 不等式**。

## 1. Young 不等式

**定理 A.0.9**（Young 不等式）：设 $a,b\ge0$，$p,q>1$ 满足 $\dfrac1p+\dfrac1q=1$，则

$$
\boxed{\;ab\le\frac{a^p}{p}+\frac{b^q}{q}\;}
$$

等号成立当且仅当 $a^p=b^q$。特别地，当 $p=q=2$ 时，即为熟知的 Cauchy 不等式：$ab\le\frac12(a^2+b^2)$。

*证明 3.A*（定理 A.0.9）：当 $a=0$ 或 $b=0$ 时不等式显然成立。设 $a>0$ 且 $b>0$。由对数函数的严格凹性，对 $s=\frac1p\in(0,1)$，$t=\frac1q=1-s$：

$$
\ln\left(\frac{a^p}{p}+\frac{b^q}{q}\right)\ge\frac1p\ln a^p+\frac1q\ln b^q=\ln a+\ln b=\ln(ab),
$$

其中不等式来自 $\ln$ 在 $s,t$ 处的加权凹性（对凸组合 $\frac{a^p}{p}+\frac{b^q}{q}$ 取对数）。由对数函数单调增，得

$$
ab\le\frac{a^p}{p}+\frac{b^q}{q}.
$$

当 $a^p=b^q$ 时取等号（此时 $\frac{a^p}{p}+\frac{b^q}{q}=a^pb^{q/q}=ab$，亦由 $\ln$ 严格凹性知等号条件唯一）。$\boxed{\sigma_\omega\sigma}$

**加权形式**：通过尺度变换——以 $\varepsilon^{1/p}a$ 代 $a$、$\varepsilon^{-1/q}b$ 代 $b$，代入 Young 不等式：

$$
(\varepsilon^{1/p}a)(\varepsilon^{-1/q}b)\le\frac{\varepsilon\,a^p}{p}+\frac{\varepsilon^{-q/p}b^q}{q},
$$

即

$$
ab\le\frac{\varepsilon a^p}{p}+\frac{\varepsilon^{-q/p}b^q}{q},\qquad\forall\varepsilon>0.\tag{A.0.2}
$$

此形式在处理含参估计时极为有用（如先验估计中通过选择 $\varepsilon$ 吸收小项）。

## 2. Hölder 不等式

Young 不等式的重要推论是下述 Hölder 不等式，它把 Cauchy–Schwarz 不等式推广到一般的 $L^p$ 空间。

**定理 A.0.10**（Hölder 不等式）：设 $\Omega\subset\mathbb R^n$ 可测，$u\in L^p(\Omega)$，$v\in L^q(\Omega)$，其中 $1\le p,q\le\infty$ 满足 $\dfrac1p+\dfrac1q=1$，则

$$
\boxed{\;\int_\Omega|uv|\,\mathrm dx\le\|u\|_{L^p(\Omega)}\,\|v\|_{L^q(\Omega)}\;}\tag{A.0.3}
$$

当 $p=q=2$ 时即为 Cauchy–Schwarz 不等式。

*证明 3.B*（定理 A.0.10）：若 $\|u\|_{L^p(\Omega)}=0$ 或 $\|v\|_{L^q(\Omega)}=+\infty$，则 (A.0.3) 显然成立。当 $p=1,q=+\infty$ 或 $p=+\infty,q=1$ 时，结论由本性上界定义直接得到。下设 $1<p,q<+\infty$。

由 Young 不等式，对 $x\in\Omega$（将 $a=\dfrac{|u(x)|}{\|u\|_{L^p}}$，$b=\dfrac{|v(x)|}{\|v\|_{L^q}}$ 代入）：

$$
\frac{|u(x)v(x)|}{\|u\|_{L^p(\Omega)}\,\|v\|_{L^q(\Omega)}}\le\frac1p\left(\frac{|u(x)|}{\|u\|_{L^p(\Omega)}}\right)^p+\frac1q\left(\frac{|v(x)|}{\|v\|_{L^q(\Omega)}}\right)^q.
$$

两边在 $\Omega$ 上积分得

$$
\frac{1}{\|u\|_{L^p}\|v\|_{L^q}}\int_\Omega|uv|\,\mathrm dx
\le\frac1p\cdot\frac{\int_\Omega|u|^p}{\|u\|_{L^p}^p}+\frac1q\cdot\frac{\int_\Omega|v|^q}{\|v\|_{L^q}^q}
=\frac1p+\frac1q=1.
$$

即得结论。$\boxed{\sigma_\omega\sigma}$

Hölder 不等式可以导出以下简单推论，它们反映了 $L^p$ 范数在不同指标下的关系。

**推论 A.0.11**（$L^p$ 空间的嵌入关系）：设 $\Omega\subset\mathbb R^n$ 为有限测度区域，$|\Omega|<+\infty$。

（1）**单调性**：若 $1\le p\le q\le+\infty$，则

$$
\|u\|_{L^p(\Omega)}\le|\Omega|^{\frac1p-\frac1q}\,\|u\|_{L^q(\Omega)}.
$$

（2）**插值不等式**：若 $0\le\theta\le1$，$\dfrac1s=\dfrac{\theta}{p}+\dfrac{1-\theta}{q}$，则

$$
\|u\|_{L^s(\Omega)}\le\|u\|_{L^p(\Omega)}^{\theta}\,\|u\|_{L^q(\Omega)}^{1-\theta}.\tag{A.0.4}
$$

（3）**加权插值**：对任意 $\varepsilon>0$，存在 $\mu>0$ 使得

$$
\|u\|_{L^r(\Omega)}\le\varepsilon\|u\|_{L^q(\Omega)}+\varepsilon^{-\mu}\|u\|_{L^p(\Omega)},
$$

其中 $p<r<q$ 且 $\dfrac1r=\dfrac{\lambda}{p}+\dfrac{1-\lambda}{q}$（$0<\lambda<1$），$\mu=\dfrac{1-\lambda}{\lambda}$。

*证明 3.C*（推论 A.0.11）：

（1）取 $v\equiv1$，应用 Hölder 不等式：

$$
\int_\Omega|u|^p\,\mathrm dx=\int_\Omega |u|^p\cdot1\,\mathrm dx
\le\left(\int_\Omega(|u|^p)^{\frac qp}\,\mathrm dx\right)^{\frac pq}|\Omega|^{1-\frac pq}
=\|u\|_{L^q(\Omega)}^p\,|\Omega|^{1-\frac pq},
$$

开 $p$ 次方即得。此结论表明：在有限测度空间上，$L^q$ 范数控制 $L^p$ 范数（$q\ge p$）。

（2）令 $\dfrac1s=\dfrac{\theta}{p}+\dfrac{1-\theta}{q}$，取共轭指数使

$$
|u|^s=|u|^{s\theta}\,|u|^{s(1-\theta)},
$$

对 $|u|^{s\theta}$ 与 $|u|^{s(1-\theta)}$ 应用 Hölder 不等式，配指标使 $\dfrac{1}{p/(s\theta)}+\dfrac{1}{q/(s(1-\theta))}=1$（由 $\theta p/s+(1-\theta)q/s=1$），得

$$
\int_\Omega|u|^s\,\mathrm dx
\le\left(\int_\Omega|u|^{s\theta\cdot\frac{p}{s\theta}}\right)^{\frac{s\theta}{p}}\left(\int_\Omega|u|^{s(1-\theta)\cdot\frac{q}{s(1-\theta)}}\right)^{\frac{s(1-\theta)}{q}}
=\|u\|_{L^p}^{s\theta}\,\|u\|_{L^q}^{s(1-\theta)},
$$

开 $s$ 次方即得。此插值关系在正则性理论中至关重要。

（3）结合 Young 不等式的加权形式（A.0.2）和插值不等式（A.0.4）即得。具体地，取 $\lambda$ 使 $\dfrac1r=\dfrac{\lambda}{p}+\dfrac{1-\lambda}{q}$，由（2）$\|u\|_{L^r}\le\|u\|_{L^p}^{\lambda}\|u\|_{L^q}^{1-\lambda}$；记 $X=\|u\|_{L^q}^{1-\lambda}$，$Y=\|u\|_{L^p}^{\lambda}$，对 $XY$ 应用加权 Young 不等式即可将混合项拆分为 $\varepsilon\|u\|_{L^q}+\varepsilon^{-\mu}\|u\|_{L^p}$。这种估计在偏微分方程的先验估计中极为有效。$\boxed{\sigma_\omega\sigma}$

> **几何 / 物理意义**：Hölder 不等式及其推论构成 $L^p$ 空间理论的基础框架，为 Sobolev 嵌入定理提供核心工具，在椭圆方程解的正则性研究中起关键作用。插值不等式是处理非线性项的有力武器——它在不同的可积性指标之间搭建桥梁，允许把"弱信息"（低可积性）与"强信息"（高可积性）加权组合成所需估计；这些不等式共同构成了现代偏微分方程理论的基石。
