# 附录 A.0.2 磨光核与函数光滑逼近

在偏微分方程理论中，**磨光核**是一种基本工具，用于构造光滑函数逼近给定函数。这种技术对于处理非光滑函数（如 Sobolev 空间中的函数）和证明正则性定理至关重要。

## 1. 标准磨光核与磨光逼近

**定义 A.0.5**（标准磨光核）：

（1）定义无穷次可微函数 $\eta\in C^\infty(\mathbb R^n)$：

$$
\eta(x):=
\begin{cases}
C\exp\left(\dfrac{1}{|x|^2-1}\right), & |x|<1,\\[6pt]
0, & |x|\ge 1,
\end{cases}
$$

其中归一化常数 $C>0$ 满足

$$
\int_{\mathbb R^n}\eta\,\mathrm dx=1,\qquad C=\left(\int_{B(0,1)}\exp\frac{1}{|x|^2-1}\,\mathrm dx\right)^{-1}.
$$

该函数具有**紧支集** $\mathrm{supp}\,\eta\subset B(0,1)$，且在原点附近急剧衰减，光滑连接。

（2）对任意 $\varepsilon>0$，定义**尺度化的磨光子**

$$
\eta_\varepsilon(x):=\varepsilon^{-n}\eta\!\left(\frac{x}{\varepsilon}\right).
$$

函数 $\eta_\varepsilon$ 是光滑的，$\mathrm{supp}\,\eta_\varepsilon\subset B(0,\varepsilon)$，且满足

$$
\int_{\mathbb R^n}\eta_\varepsilon\,\mathrm dx=1.
$$

**定义 A.0.6**（函数的磨光逼近）：设 $\Omega\subset\mathbb R^n$ 为开集，$f:\Omega\to\mathbb R$ 局部可积。对 $\varepsilon>0$，定义其**磨光版本**

$$
f^\varepsilon(x):=\eta_\varepsilon\ast f(x)=\int_{\Omega}\eta_\varepsilon(x-y)\,f(y)\,\mathrm dy,
$$

其中 $\Omega_\varepsilon:=\{x\in\Omega:\ \mathrm{dist}(x,\partial\Omega)>\varepsilon\}$ 是 $\Omega$ 的**内缩区域**（避免边界效应）。

## 2. 磨光函数的性质

**定理 A.0.7**（磨光函数的性质）：设 $f$ 局部可积，则磨光逼近具有以下性质：

（1）**无穷可微性**：$f^\varepsilon\in C^\infty(\Omega_\varepsilon)$；

（2）**逐点收敛**：当 $\varepsilon\to0^+$ 时，$f^\varepsilon(x)\to f(x)$ 对几乎所有 $x\in\Omega$ 成立；

（3）**一致收敛**：若 $f$ 连续，则 $f^\varepsilon\to f$ 在 $\Omega$ 的任意紧子集上一致收敛；

（4）**$L^p$ 收敛**：若 $f\in L^p_{\mathrm{loc}}(\Omega)$（$1\le p<+\infty$），则 $f^\varepsilon\to f$ 在 $L^p_{\mathrm{loc}}(\Omega)$ 中收敛。

*证明 2.A*（定理 A.0.7）：为证明（1），固定 $x\in\Omega_\varepsilon$，$i\in\{1,2,\dots,n\}$，取 $h$ 充分小使 $x+h\boldsymbol e_i\in\Omega_\varepsilon$。对 $\Omega$ 的某个紧子集 $V\subset\subset\Omega$，考虑差商

$$
\frac{f^\varepsilon(x+h\boldsymbol e_i)-f^\varepsilon(x)}{h}
=\int_{\Omega}\frac{\eta_\varepsilon(x+h\boldsymbol e_i-y)-\eta_\varepsilon(x-y)}{h}\,f(y)\,\mathrm dy.
$$

因为 $\dfrac{\eta_\varepsilon(\cdot+h\boldsymbol e_i)-\eta_\varepsilon(\cdot)}{h}$ 在 $V$ 上一致收敛到 $\partial_{x_i}\eta_\varepsilon$，由含参量积分的可微性，偏导数 $f^\varepsilon_{x_i}(x)$ 存在且等于

$$
\partial_{x_i}f^\varepsilon(x)=\int_{\Omega}\partial_{x_i}\eta_\varepsilon(x-y)\,f(y)\,\mathrm dy.
$$

通过归纳可得任意阶导数存在：对每一个多重指标 $\alpha$，$D^\alpha f^\varepsilon$ 存在，且

$$
D^\alpha f^\varepsilon(x)=\int_{\Omega}D^\alpha\eta_\varepsilon(x-y)\,f(y)\,\mathrm dy,\qquad x\in\Omega_\varepsilon.
$$

故 $f^\varepsilon\in C^\infty(\Omega_\varepsilon)$。（1）证毕。

在证明（2）之前，我们先回顾 **Lebesgue 微分定理**。

**定理 A.0.8**（Lebesgue 微分定理）：设 $f:\mathbb R^n\to\mathbb R$ 局部可积，则

（i）对于几乎所有的 $x_0\in\mathbb R^n$，

$$
\frac{1}{|B(x_0,r)|}\int_{B(x_0,r)}f\,\mathrm dx\to f(x_0),\qquad \text{当}\ r\to0;
$$

（ii）实际上，对于几乎所有的 $x_0\in\mathbb R^n$，

$$
\frac{1}{|B(x_0,r)|}\int_{B(x_0,r)}|f(x)-f(x_0)|\,\mathrm dx\to0,\qquad \text{当}\ r\to0.
$$

点 $x_0$ 称为 $f$ 的 **Lebesgue 点**。更一般地，若 $f\in L^p_{\mathrm{loc}}(\mathbb R^n)$，$1\le p<+\infty$，则对几乎所有的 $x_0\in\mathbb R^n$，

$$
\frac{1}{|B(x_0,r)|}\int_{B(x_0,r)}|f(x)-f(x_0)|^p\,\mathrm dx\to0,\qquad \text{当}\ r\to0.
$$

现在证明（2）。对 Lebesgue 点 $x\in\Omega$，

$$
\begin{aligned}
|f^\varepsilon(x)-f(x)|
&=\left|\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,[f(y)-f(x)]\,\mathrm dy\right|\\
&\le\frac{C}{\varepsilon^n}\int_{B(x,\varepsilon)}|f(y)-f(x)|\,\mathrm dy
=\frac{C}{\alpha(n)}\frac{1}{|B(x,\varepsilon)|}\int_{B(x,\varepsilon)}|f(y)-f(x)|\,\mathrm dy\to0,\qquad\text{当}\ \varepsilon\to0,
\end{aligned}
$$

其中最后一步由 Lebesgue 微分定理（ii）。(2)证毕。

（3）当 $f$ 连续时，取 $V\subset\subset U\subset\subset\Omega$，$f$ 在紧集 $\bar U$ 上一致连续，故在 $U$ 上可积且有**一致的连续模**。于是极限

$$
\lim_{r\to0}\frac{1}{|B(x,r)|}\int_{B(x,r)}|f(y)-f(x)|\,\mathrm dy=0
$$

对 $x\in V$ 一致成立。由（2）的推导可见 $f^\varepsilon\to f$ 在 $V$ 上一致收敛。(3)证毕。

（4）设 $1\le p<+\infty$，$f\in L^p_{\mathrm{loc}}(\Omega)$。取 $V\subset\subset U\subset\subset\Omega$。对充分小的 $\varepsilon>0$，先建立关键估计（A.0.1）：

$$
\|f^\varepsilon\|_{L^p(V)}\le\|f\|_{L^p(U)}.\tag{A.0.1}
$$

事实上，若 $1\le p<+\infty$，$x\in V$，由 Hölder 不等式（见附录 A.0.3）及 $\int\eta_\varepsilon=1$：

$$
\begin{aligned}
|f^\varepsilon(x)|
&=\left|\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,f(y)\,\mathrm dy\right|
\le\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,|f(y)|\,\mathrm dy\\
&\le\left(\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,\mathrm dy\right)^{1-\frac1p}\left(\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,|f(y)|^p\,\mathrm dy\right)^{\frac1p}
=\left(\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,|f(y)|^p\,\mathrm dy\right)^{\frac1p}.
\end{aligned}
$$

所以，对充分小的 $\varepsilon>0$（使 $x\pm\varepsilon\subset U$），

$$
\int_V|f^\varepsilon(x)|^p\,\mathrm dx
\le\int_V\left(\int_{B(x,\varepsilon)}\eta_\varepsilon(x-y)\,|f(y)|^p\,\mathrm dy\right)\mathrm dx
=\int_U|f(y)|^p\left(\int_V\eta_\varepsilon(x-y)\,\mathrm dx\right)\mathrm dy\le\int_U|f(y)|^p\,\mathrm dy.
$$

即 (A.0.1) 成立。

现在固定 $V\subset\subset U\subset\subset\Omega$，$\delta>0$，取 $g\in C(\bar U)$ 使得 $\|f-g\|_{L^p(U)}<\delta$（光滑函数在 $L^p$ 中稠密）。则

$$
\|f^\varepsilon-f\|_{L^p(V)}\le\|f^\varepsilon-g^\varepsilon\|_{L^p(V)}+\|g^\varepsilon-g\|_{L^p(V)}+\|g-f\|_{L^p(V)}
\le2\|f-g\|_{L^p(U)}+\|g^\varepsilon-g\|_{L^p(V)}
\le2\delta+\|g^\varepsilon-g\|_{L^p(V)}.
$$

因为 $g$ 在 $\bar U$ 上一致连续，由（3）$g^\varepsilon\to g$ 在 $V$ 上一致收敛，故

$$
\limsup_{\varepsilon\to0}\|f^\varepsilon-f\|_{L^p(V)}\le2\delta.
$$

由 $\delta>0$ 的任意性，(4)证毕。$\boxed{\sigma_\omega\sigma}$

> **几何 / 物理意义**：磨光核技术为分布理论提供了函数逼近工具，是证明 Sobolev 嵌入定理的基础，在椭圆方程正则性理论中起关键作用。其核心价值在于：通过积分算子将非光滑函数转化为光滑函数，同时保持函数的本质特征（$L^p$ 模、积分均值等不损失信息），从而为弱解的正则性提升提供基本框架（正文 2.2 节均值性质→光滑性的证明正是依赖此法）。
