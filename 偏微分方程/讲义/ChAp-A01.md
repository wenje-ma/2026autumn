# 附录 A.0.1 梯度定理

梯度定理（又称**曲线积分基本定理**）是微积分基本定理在曲线积分中的推广，建立了标量场与向量场之间的深刻联系。它在保守力场与势能理论中具有广泛应用。本附录将其与逆定理一并整理，并给出两个典型例题。

## 1. 梯度定理

**定理 A.0.1**（梯度定理）：设 $U\subset\mathbb R^n$ 为开集，$\varphi:U\to\mathbb R$ 可微，$\boldsymbol\gamma:[a,b]\to U$ 是 $U$ 中连接 $p,q$ 的可微曲线（即 $\boldsymbol\gamma(a)=p$，$\boldsymbol\gamma(b)=q$）。则曲线积分满足

$$
\boxed{\;\int_{\boldsymbol\gamma}\nabla\varphi(\boldsymbol x)\cdot\mathrm d\boldsymbol r=\varphi(q)-\varphi(p)\;}
$$

*证明 1.A*（定理 A.0.1）：考虑参数化曲线 $\boldsymbol\gamma:[a,b]\to U$。由链式法则，对 $t\in[a,b]$，

$$
\frac{\mathrm d}{\mathrm dt}\varphi\bigl(\boldsymbol\gamma(t)\bigr)=\nabla\varphi\bigl(\boldsymbol\gamma(t)\bigr)\cdot\boldsymbol\gamma'(t).
$$

两边对 $t$ 从 $a$ 到 $b$ 积分，利用曲线积分的定义与微积分基本定理，

$$
\int_{\boldsymbol\gamma}\nabla\varphi\cdot\mathrm d\boldsymbol r=\int_a^b\nabla\varphi\bigl(\boldsymbol\gamma(t)\bigr)\cdot\boldsymbol\gamma'(t)\,\mathrm dt=\int_a^b\frac{\mathrm d}{\mathrm dt}\varphi\bigl(\boldsymbol\gamma(t)\bigr)\,\mathrm dt=\varphi\bigl(\boldsymbol\gamma(b)\bigr)-\varphi\bigl(\boldsymbol\gamma(a)\bigr)=\varphi(q)-\varphi(p).\qquad\blacksquare
$$

梯度定理揭示了两个核心性质：

- **路径无关性**：梯度场 $\nabla\varphi$ 的线积分只取决于端点 $p,q$，与路径选择无关；
- **保守场特征**：当 $\varphi$ 表示势函数时，$\nabla\varphi$ 对应守恒力场（如重力场、静电场）。

**例题 A.0.2**（圆弧上的积分）：计算沿圆弧 $\boldsymbol\gamma$（从 $(5,0)$ 到 $(-4,3)$，半径为 $5$）的积分

$$
\int_{\boldsymbol\gamma}y\,\mathrm dx+x\,\mathrm dy.
$$

*解法一（常规参数化）*：取参数化 $\boldsymbol\gamma(t)=(5\cos t,5\sin t)$。端点 $(5,0)$ 对应 $t=0$，端点 $(-4,3)$ 对应 $t_0=\pi-\arctan\frac34$（因 $5\cos t_0=-4,\ 5\sin t_0=3$）。于是

$$
\begin{aligned}
\int_{\boldsymbol\gamma}y\,\mathrm dx+x\,\mathrm dy
&=\int_0^{t_0}\Bigl(5\sin t\cdot(-5\sin t)+5\cos t\cdot5\cos t\Bigr)\mathrm dt\\
&=25\int_0^{t_0}(\cos^2t-\sin^2t)\,\mathrm dt=25\int_0^{t_0}\cos 2t\,\mathrm dt\\
&=\frac{25}{2}\sin(2t_0)=\frac{25}{2}\sin\bigl(2\pi-2\arctan\tfrac34\bigr)=-\frac{25}{2}\sin\bigl(2\arctan\tfrac34\bigr).
\end{aligned}
$$

由 $\sin\bigl(2\arctan\tfrac34\bigr)=\dfrac{2\cdot\frac34}{1+\frac{9}{16}}=\dfrac{24}{25}$，得

$$
\int_{\boldsymbol\gamma}y\,\mathrm dx+x\,\mathrm dy=-12.
$$

*解法二（梯度定理）*：注意到被积函数恰为 $xy$ 的梯度 $\nabla(xy)=(y,x)$。由梯度定理，积分只取决于端点：

$$
\int_{\boldsymbol\gamma}y\,\mathrm dx+x\,\mathrm dy=xy\Big|_{(5,0)}^{(-4,3)}=(-4\cdot3)-(5\cdot0)=-12.
$$

梯度定理将曲线积分转化为端点求值，大幅简化计算。$\blacksquare$

**例题 A.0.3**（克服点电荷电场做功）：计算将电荷 $q$ 从 $\boldsymbol a$ 移动到 $\boldsymbol b$ 时，克服 $n$ 个点电荷 $Q_i$ 产生的静电场所做的功。

*解 1.B*：由 Coulomb 定律，电荷 $q$ 在位置 $\boldsymbol r$ 所受电场力为

$$
\boldsymbol F(\boldsymbol r)=kq\sum_{i=1}^n\frac{Q_i(\boldsymbol r-\boldsymbol P_i)}{|\boldsymbol r-\boldsymbol P_i|^3},\qquad k=\frac{1}{4\pi\varepsilon_0}\ (\text{真空电容率}).
$$

做功为路径积分。设 $\boldsymbol\gamma\subset\mathbb R^3\setminus\{\boldsymbol P_1,\dots,\boldsymbol P_n\}$ 是连接 $\boldsymbol a,\boldsymbol b$ 的任意可微曲线，则对粒子做的功

$$
W=\int_{\boldsymbol\gamma}\boldsymbol F(\boldsymbol r)\cdot\mathrm d\boldsymbol r=kq\sum_{i=1}^n Q_i\int_{\boldsymbol\gamma}\frac{\boldsymbol r-\boldsymbol P_i}{|\boldsymbol r-\boldsymbol P_i|^3}\cdot\mathrm d\boldsymbol r.
$$

对每个 $i$，被积向量场是标量函数 $\dfrac{1}{|\boldsymbol r-\boldsymbol P_i|}$ 的梯度（差一个符号）：

$$
\nabla\left(\frac{1}{|\boldsymbol r-\boldsymbol P_i|}\right)=-\frac{\boldsymbol r-\boldsymbol P_i}{|\boldsymbol r-\boldsymbol P_i|^3},
$$

故由梯度定理（关键步骤：识别被积函数为势函数的梯度，将路径积分转化为端点势能差）

$$
\int_{\boldsymbol\gamma}\frac{\boldsymbol r-\boldsymbol P_i}{|\boldsymbol r-\boldsymbol P_i|^3}\cdot\mathrm d\boldsymbol r
=-\int_{\boldsymbol\gamma}\nabla\left(\frac{1}{|\boldsymbol r-\boldsymbol P_i|}\right)\cdot\mathrm d\boldsymbol r
=\frac{1}{|\boldsymbol a-\boldsymbol P_i|}-\frac{1}{|\boldsymbol b-\boldsymbol P_i|}.
$$

电场力本身做的功为 $\int_{\boldsymbol\gamma}\boldsymbol F\cdot\mathrm d\boldsymbol r$；题目所求为**克服**电场力所做的功，即 $W=-\int_{\boldsymbol\gamma}\boldsymbol F\cdot\mathrm d\boldsymbol r$，于是

$$
\boxed{\;W=-kq\sum_{i=1}^n Q_i\int_{\boldsymbol\gamma}\frac{\boldsymbol r-\boldsymbol P_i}{|\boldsymbol r-\boldsymbol P_i|^3}\cdot\mathrm d\boldsymbol r
=kq\sum_{i=1}^n Q_i\left(\frac{1}{|\boldsymbol b-\boldsymbol P_i|}-\frac{1}{|\boldsymbol a-\boldsymbol P_i|}\right)\;}
$$

## 2. 梯度定理的逆定理

梯度定理表明：若向量场 $\boldsymbol F$ 是某标量函数的梯度，则 $\boldsymbol F$ 与路径无关。其逆定理揭示了保守场的本质特征。

**定理 A.0.4**（梯度定理的逆定理）：若向量场 $\boldsymbol F:U\to\mathbb R^n$ 与路径无关（即线积分只取决于端点），则存在标量函数 $\varphi:U\to\mathbb R$，使得 $\boldsymbol F=\nabla\varphi$。

*证明 1.C*（定理 A.0.4）：设 $U$ 是 $\mathbb R^n$ 中道路连通的开子集，$\boldsymbol F:U\to\mathbb R^n$ 是连续且与路径无关的向量场。固定一点 $\boldsymbol a_0\in U$，定义 $\varphi:U\to\mathbb R$：

$$
\varphi(\boldsymbol x):=\int_{\boldsymbol\gamma[\boldsymbol a_0,\boldsymbol x]}\boldsymbol F(\boldsymbol u)\cdot\mathrm d\boldsymbol u,
$$

其中 $\boldsymbol\gamma[\boldsymbol a_0,\boldsymbol x]$ 是 $U$ 中以 $\boldsymbol a_0$ 为起点、$\boldsymbol x$ 为终点的任意可微曲线。由与路径无关性，$\varphi$ 良定义。

取方向向量 $\boldsymbol v$，计算方向导数：

$$
\partial_{\boldsymbol v}\varphi(\boldsymbol x)=\lim_{t\to0}\frac{\varphi(\boldsymbol x+t\boldsymbol v)-\varphi(\boldsymbol x)}{t}
=\lim_{t\to0}\frac{1}{t}\left(\int_{\boldsymbol\gamma[\boldsymbol a_0,\boldsymbol x+t\boldsymbol v]}\boldsymbol F\cdot\mathrm d\boldsymbol u-\int_{\boldsymbol\gamma[\boldsymbol a_0,\boldsymbol x]}\boldsymbol F\cdot\mathrm d\boldsymbol u\right)
=\lim_{t\to0}\frac{1}{t}\int_{\boldsymbol\gamma[\boldsymbol x,\boldsymbol x+t\boldsymbol v]}\boldsymbol F(\boldsymbol u)\cdot\mathrm d\boldsymbol u.
$$

因 $\boldsymbol F$ 与路径无关、$U$ 是开集且 $t\to0$，可取该段路径为直线段 $\boldsymbol\gamma(s)=\boldsymbol x+s\boldsymbol v\ (0\le s\le t)$。由于 $\boldsymbol\gamma'(s)=\boldsymbol v$ 及 $\boldsymbol F$ 的连续性，

$$
\lim_{t\to0}\frac{1}{t}\int_0^t\boldsymbol F(\boldsymbol x+s\boldsymbol v)\cdot\boldsymbol v\,\mathrm ds=\boldsymbol F(\boldsymbol x)\cdot\boldsymbol v.
$$

由于 $\boldsymbol v$ 任意，取 $\boldsymbol v=\boldsymbol e_i$ 得

$$
\frac{\partial\varphi}{\partial x_i}(\boldsymbol x)=\boldsymbol F(\boldsymbol x)\cdot\boldsymbol e_i=F_i(\boldsymbol x),
$$

故 $\nabla\varphi(\boldsymbol x)=(F_1(\boldsymbol x),\dots,F_n(\boldsymbol x))=\boldsymbol F(\boldsymbol x)$。这样我们找到了一个标量函数 $\varphi$，其梯度等于与路径无关的向量场 $\boldsymbol F$。$\blacksquare$

梯度定理及其逆定理共同表明：

> **几何 / 物理意义**：力场是保守的，当且仅当它是某个势函数的梯度；保守场等价于梯度场，亦等价于与路径无关的场。在保守场中，沿闭合路径做功为零——这是能量守恒的数学基础。这组定理构成向量分析的核心支柱，为电磁学、流体力学中的势函数理论提供了基础工具（流体力学中速度势的定义正源于梯度定理，见第 1 章）。
