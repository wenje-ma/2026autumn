# 作业 1

## 1

设 $\boldsymbol{a}(t)$ 是向量值函数，证明：

（1）$|\boldsymbol{a}|$ 为常数当且仅当 $\langle \boldsymbol{a}(t),\boldsymbol{a}'(t)\rangle=0$；

（2）$\boldsymbol{a}(t)$ 的方向不变当且仅当 $\boldsymbol{a}(t)\wedge \boldsymbol{a}'(t)=\boldsymbol{0}$。

### 解答

（1）对 $\|\boldsymbol{a}\|^{2}=\langle\boldsymbol{a},\boldsymbol{a}\rangle$ 求导：

$$
\frac{\mathrm d}{\mathrm dt}\|\boldsymbol{a}(t)\|^{2}=\frac{\mathrm d}{\mathrm dt}\langle\boldsymbol{a},\boldsymbol{a}\rangle=\langle\boldsymbol{a}',\boldsymbol{a}\rangle+\langle\boldsymbol{a},\boldsymbol{a}'\rangle=2\langle\boldsymbol{a},\boldsymbol{a}'\rangle
$$

（$\Rightarrow$）若 $|\boldsymbol{a}|$ 为常数，则 $\|\boldsymbol{a}\|^{2}$ 亦为常数，故 $\frac{\mathrm d}{\mathrm dt}\|\boldsymbol{a}\|^{2}=0$，从而 $\langle\boldsymbol{a},\boldsymbol{a}'\rangle=0$。

（$\Leftarrow$）反之，若 $\langle\boldsymbol{a},\boldsymbol{a}'\rangle=0$，则 $\frac{\mathrm d}{\mathrm dt}\|\boldsymbol{a}\|^{2}=0$，故 **$\|\boldsymbol{a}\|^{2}$ 为常数，$|\boldsymbol{a}|$ 为常数**。$\boxed{\sigma_\omega\sigma}$

（2）设 $\boldsymbol a\ne\boldsymbol 0$（否则方向无定义）。

（$\Rightarrow$）设方向不变，则存在固定的单位向量 $\boldsymbol v$ 与数量函数 $f(t)$，使 $\boldsymbol a(t)=f(t)\boldsymbol v$。则 $\boldsymbol a'(t)=f'(t)\boldsymbol v$，于是

$$
\boldsymbol a(t)\wedge\boldsymbol a'(t)=f(t)f'(t)(\boldsymbol v\wedge\boldsymbol v)=\boldsymbol 0
$$

（$\Leftarrow$）若 $\boldsymbol a\wedge\boldsymbol a'=\boldsymbol 0$，则 $\boldsymbol a'$ 与 $\boldsymbol a$ 共线：存在数量函数 $\mu(t)$ 使 $\boldsymbol a'=\mu(t)\boldsymbol a$。令 $\boldsymbol u(t):=\frac{\boldsymbol a(t)}{\|\boldsymbol a(t)\|}$ 为方向单位向量。由（1），

$$
\frac{\mathrm d}{\mathrm dt}\|\boldsymbol a\|=\frac{\langle\boldsymbol a,\boldsymbol a'\rangle}{\|\boldsymbol a\|}=\frac{\mu\langle\boldsymbol a,\boldsymbol a\rangle}{\|\boldsymbol a\|}=\mu\|\boldsymbol a\|
$$

于是

$$
\boldsymbol u'=\frac{\boldsymbol a'}{\|\boldsymbol a\|}-\frac{\boldsymbol a(\|\boldsymbol a\|)'}{\|\boldsymbol a\|^{2}}=\frac{\mu\boldsymbol a}{\|\boldsymbol a\|}-\frac{\boldsymbol a\mu\|\boldsymbol a\|}{\|\boldsymbol a\|^{2}}=\boldsymbol 0
$$

故 $\boldsymbol u$ 为常向量，即 **$\boldsymbol a$ 的方向不变**。$\boxed{\sigma_\omega\sigma}$

---

## 2

（1）设 $\boldsymbol\alpha:I\to\mathbb R^3\cong E^3$ 是连续曲线（即 $\boldsymbol\alpha$ 的分量函数都是连续的），以及 $[a,b]$ 是包含在 $I$ 中的闭区间。对于 $[a,b]$ 的任意划分 $P:a=t_0<t_1<\dots<t_n=b$，定义

$$
L(\boldsymbol\alpha,P):=\sum_{i=1}^n|\boldsymbol\alpha(t_i)-\boldsymbol\alpha(t_{i-1})|
$$

进一步定义曲线 $\boldsymbol\alpha$ 从 $a$ 到 $b$ 的弧长 $L(\boldsymbol\alpha,[a,b])$ 为对于 $[a,b]$ 上的所有划分 $P$，$L(\boldsymbol\alpha,P)$ 的上确界，即

$$
L(\boldsymbol\alpha,[a,b]):=\sup_P L(\boldsymbol\alpha,P)
$$

证明：若 $\boldsymbol\alpha:I\to\mathbb R^3$ 是光滑曲线，则

$$
L(\boldsymbol\alpha,[a,b])=\int_a^b|\boldsymbol\alpha'(t)|\mathrm dt
$$

（2）证明 $\mathbb R^3$ 中任何两点之间直线最短。

### 解答

（1）对任意划分 $P:a=t_0<t_1<\dots<t_n=b$，由微积分基本定理

$$
\boldsymbol\alpha(t_i)-\boldsymbol\alpha(t_{i-1})=\int_{t_{i-1}}^{t_i}\boldsymbol\alpha'(t)\mathrm dt
$$

故

$$
|\boldsymbol\alpha(t_i)-\boldsymbol\alpha(t_{i-1})|=\left|\int_{t_{i-1}}^{t_i}\boldsymbol\alpha'\mathrm dt\right|\le\int_{t_{i-1}}^{t_i}|\boldsymbol\alpha'|\mathrm dt
$$

对 $i=1,\dots,n$ 求和得 $L(\boldsymbol\alpha,P)\le\int_a^b|\boldsymbol\alpha'|\mathrm dt$，故

$$
L(\boldsymbol\alpha,[a,b])=\sup_P L(\boldsymbol\alpha,P)\le\int_a^b|\boldsymbol\alpha'|\mathrm dt
$$

反之，因 $\boldsymbol\alpha$ 光滑，$|\boldsymbol\alpha'|$ 连续、从而在 $[a,b]$ 上一致连续。对给定 $\epsilon>0$，取充分细的划分，使在每个子区间 $[t_{i-1},t_i]$ 上

$$
|\boldsymbol\alpha'(t)-\boldsymbol\alpha'(t_{i-1})|<\epsilon
$$

则依据反向三角不等式 $|x+y|\ge|x|-|y|$ 有

$$
\begin{aligned}
|\boldsymbol\alpha(t_i)-\boldsymbol\alpha(t_{i-1})|
&=\left|\int_{t_{i-1}}^{t_i}\boldsymbol\alpha'(t)\mathrm dt\right|\\
&\ge\left|\int_{t_{i-1}}^{t_i}\boldsymbol\alpha'(t_{i-1})\mathrm dt\right|
-\left|\int_{t_{i-1}}^{t_i}\big[\boldsymbol\alpha'(t)-\boldsymbol\alpha'(t_{i-1})\big]\mathrm dt\right|\\
&\ge|\boldsymbol\alpha'(t_{i-1})|(t_i-t_{i-1})-\epsilon(t_i-t_{i-1})
\end{aligned}
$$

对 $i$ 求和并令划分加密：由 $|\boldsymbol\alpha'|$ 连续，黎曼和 $\sum_i|\boldsymbol\alpha'(t_{i-1})|(t_i-t_{i-1})\to\int_a^b|\boldsymbol\alpha'|\mathrm dt$，故

$$
L(\boldsymbol\alpha,[a,b])=\sup_P L(\boldsymbol\alpha,P)\ge\int_a^b|\boldsymbol\alpha'|\mathrm dt-\epsilon(b-a)
$$

由 $\epsilon>0$ 任意，得 $L(\boldsymbol\alpha,[a,b])\ge\int_a^b|\boldsymbol\alpha'|\mathrm dt$。两方向结合即

$$
\boxed{L(\boldsymbol\alpha,[a,b])=\int_a^b|\boldsymbol\alpha'|\mathrm dt}\quad\boxed{\sigma_\omega\sigma}
$$

（2）设 $\boldsymbol\alpha:[a,b]\to\mathbb R^3$ 是连接两点 $P=\boldsymbol\alpha(a)$、$Q=\boldsymbol\alpha(b)$ 的任意曲线。直线段可参数化为

$$
\boldsymbol\gamma(t)=P+\frac{t-a}{b-a}(Q-P),\quad t\in[a,b]
$$

则 $\boldsymbol\gamma'=\frac{Q-P}{b-a}$，其弧长为

$$
\int_a^b|\boldsymbol\gamma'|\mathrm dt=\int_a^b\frac{|Q-P|}{b-a}\mathrm dt=|Q-P|
$$

对任意连接 $P,Q$ 的曲线 $\boldsymbol\alpha$，由（1）及 $\left|\int f\right|\le\int|f|$：

$$
L(\boldsymbol\alpha,[a,b])=\int_a^b|\boldsymbol\alpha'|\mathrm dt\ge\left|\int_a^b\boldsymbol\alpha'\mathrm dt\right|=|\boldsymbol\alpha(b)-\boldsymbol\alpha(a)|=|Q-P|
$$

故任何连接两点的曲线长度都不小于 $|Q-P|$，而直线段恰好达到 $|Q-P|$，所以 **$\mathbb R^3$ 中任何两点之间直线最短**。$\boxed{\sigma_\omega\sigma}$

---

## 3

（1）讨论平面曲线的几何。如平面曲线的曲率的定义，平面曲线基本定理。

> **定理 4.4**：设 $\kappa(s)$ 是连续可微函数，则 <br>（1）存在平面 $E^2$ 的曲线 $\boldsymbol{r}(s)$，它以 $s$ 为弧长参数，$\kappa(s)$ 为曲率；<br>（2）上述曲线在相差平面的一个刚体运动的意义下是唯一的。

（2）对比空间曲线的理论，谈谈你觉得平面曲线的情形有什么特别之处。

### 解答

**（1）平面曲线的几何：曲率与平面曲线基本定理。**

设 $\boldsymbol\gamma:[0,L]\to\mathbb R^2$ 是以弧长为参数的平面正则曲线。切向量

$$
\boldsymbol T(s):=\dot{\boldsymbol\gamma}(s)=\frac{\mathrm d\boldsymbol\gamma}{\mathrm ds}
$$

是单位向量；$\mathbb R^2$ 中存在唯一的单位向量 $\boldsymbol N(s)\perp\boldsymbol T(s)$，使 $\{\boldsymbol T,\boldsymbol N\}$ 构成右手系，称为曲线在 $\boldsymbol\gamma(s)$ 处的**弗雷内标架**。

由 $\|\boldsymbol T\|^{2}\equiv1$ 对 $s$ 求导得 $\dot{\boldsymbol T}\perp\boldsymbol T$；二维中垂直于 $\boldsymbol T$ 的方向只有 $\boldsymbol N$ 方向，故存在数量函数 $\kappa(s)$ 使

$$
\dot{\boldsymbol T}(s)=\kappa(s)\boldsymbol N(s),
$$

再由 $\|\boldsymbol N\|^{2}\equiv1$ 求导得 $\dot{\boldsymbol N}\perp\boldsymbol N$，由 $\langle\boldsymbol T,\boldsymbol N\rangle\equiv0$ 求导得 $\langle\dot{\boldsymbol T},\boldsymbol N\rangle+\langle\boldsymbol T,\dot{\boldsymbol N}\rangle=0$，代入前式得 $\dot{\boldsymbol N}(s)=-\kappa(s)\boldsymbol T(s)$。于是二维弗雷内方程为

$$
\frac{\mathrm d}{\mathrm ds}\begin{bmatrix}\boldsymbol T\\\boldsymbol N\end{bmatrix}
=\begin{bmatrix}0&\kappa\\-\kappa&0\end{bmatrix}\begin{bmatrix}\boldsymbol T\\\boldsymbol N\end{bmatrix},
\quad\dot{\boldsymbol\gamma}=\boldsymbol T.
$$

其中 $\kappa(s)$ 称为**有向曲率**，其绝对值 $|\kappa(s)|$ 即通常意义下的曲率。

**平面曲线基本定理**（定理 4.2）：

- （正向）设 $\boldsymbol\gamma_1,\boldsymbol\gamma_2:[0,L]\to\mathbb R^2$ 均以弧长为参数，且 $\boldsymbol\gamma_2=\boldsymbol A\boldsymbol\gamma_1+\boldsymbol\beta_0$，其中 $\boldsymbol A^{\top}\boldsymbol A=I_2$，$\boldsymbol\beta_0\in\mathbb R^2$ 为常向量，$\det\boldsymbol A=1$（保向等距），则 $\kappa_1(s)=\kappa_2(s)$。
- （逆向）给定 $\bar\kappa\in C^1([0,L])$，在保向等距变换的意义下，存在唯一正则曲线 $\boldsymbol\gamma:[0,L]\to\mathbb R^2$ 以 $\bar\kappa$ 为有向曲率。

*证明思路*：由 $\dot{\boldsymbol T}=\kappa\boldsymbol N$、$\boldsymbol N=(-\dot x^2,\dot x^1)$ 得

$$
\frac{\mathrm d}{\mathrm ds}\begin{bmatrix}\dot x^1\\\dot x^2\end{bmatrix}
=\kappa(s)\begin{bmatrix}-\dot x^2\\\dot x^1\end{bmatrix},
$$

连同 $\dot x^1,\dot x^2$ 的定义构成一阶常微分方程组；因 $\kappa\in C^1$，右端关于未知量 Lipschitz 连续，由常微分方程初值问题的存在唯一性定理得**存在性**。**唯一性（模保向等距）**：设 $\widetilde{\boldsymbol\gamma}$ 也是同一 $\kappa$ 的弧长参数曲线，取旋转矩阵 $\boldsymbol A$ 使 $\boldsymbol A\dot{\boldsymbol\gamma}(0)=\dot{\widetilde{\boldsymbol\gamma}}(0)$、平移向量 $\boldsymbol\beta_0=\widetilde{\boldsymbol\gamma}(0)-\boldsymbol A\boldsymbol\gamma(0)$，构造 $\hat{\boldsymbol\gamma}=\boldsymbol A\boldsymbol\gamma+\boldsymbol\beta_0$；由正向部分它仍以 $\kappa$ 为有向曲率，且与 $\widetilde{\boldsymbol\gamma}$ 初值相同，由初值唯一性得 $\widetilde{\boldsymbol\gamma}=\hat{\boldsymbol\gamma}$。$\boxed{\sigma_\omega\sigma}$

**（2）与空间曲线对比，平面曲线的特别之处。**

① **曲率是"有符号"的数量函数**。平面上 $\dot{\boldsymbol T}\perp\boldsymbol T$ 只有 $\boldsymbol N$ 一个正交方向，故 $\kappa$ 是标量且可正可负（有向曲率，$|\kappa|$ 为通常曲率）；而空间曲率定义为 $\kappa=\|\dot{\boldsymbol T}\|\ge0$（非负），主法向 $\boldsymbol N=\dot{\boldsymbol T}/\|\dot{\boldsymbol T}\|$ 由切向变化直接确定，无符号可言。

② **没有挠率，决定曲线只需一个函数 $\kappa$**。平面曲线基本定理：给定 $\kappa(s)$ 即（模保向等距）唯一确定曲线；而空间曲线需由 $\kappa$ 与 $\tau$ 两个函数共同决定（空间曲线基本定理，定理 5.6）。弗雷内方程也从空间的 $3\times3$ 反对称系统退化为平面的 $2\times2$ 反对称系统，只有一个函数 $\kappa$。

③ **平面曲线自动"扁平"**。空间情形中，挠率 $\tau$ 度量曲线偏离密切平面的程度，$\tau\equiv0$ 当且仅当曲线是平面曲线（命题 6.2）；而平面曲线本身落在 $\mathbb R^2$ 中，自动 $\tau\equiv0$，不需要挠率这一几何量。

④ **等距变换下曲率的"保向"敏感性**。空间曲率 $\kappa=\|\dot{\boldsymbol T}\|$ 在任意正交变换下不变，挠率 $\tau$ 在反向（反射）变换下变号；而平面有向曲率在等距变换下按 $\kappa_2=\det(\boldsymbol A)\kappa_1$ 变换（证明 4.A），反射下 $\det\boldsymbol A=-1$ 会翻转符号。因此平面曲线唯一性需"模保向等距"，空间曲线唯一性"模整个等距变换"。

综上，平面曲线之特别处在于：曲率退化为一个可带符号的标量函数、且无挠率，由单一函数 $\kappa(s)$ 模保向等距即可完全确定曲线。$\boxed{\sigma_\omega\sigma}$

---

## 4

*曲率和挠率的计算*。求下列曲线的曲率和挠率：

（1）$\boldsymbol r\left(t\right)=\left(a\cosh t,a\sinh t,bt\right)$（$a>0$）。

（3）$\boldsymbol r\left(t\right)=\left(a\left(1-\sin t\right),a\left(1-\cos t\right),bt\right)$（$a>0$）。

### 解答

依据**一般参数下的曲率与挠率公式**：

（1）$\boldsymbol r\left(t\right)=\left(a\cosh t,a\sinh t,bt\right)$（$a>0$）。

$$
\begin{aligned}
\boldsymbol r'&=\left(a\sinh t,a\cosh t,b\right)\\
v^{2}&=a^{2}\sinh^{2}t+a^{2}\cosh^{2}t+b^{2}\\
&=a^{2}\cosh 2t+b^{2}\\
\boldsymbol r''&=\left(a\cosh t,a\sinh t,0\right)\\
\boldsymbol r'''&=\left(a\sinh t,a\cosh t,0\right)\\
\boldsymbol r'\times \boldsymbol r''&=\left(-ab\sinh t,ab\cosh t,-a^{2}\right)\\
w^{2}&=a^{2}b^{2}\cosh 2t+a^{4}\\
w&=a\sqrt{a^{2}+b^{2}\cosh 2t}\\
\left(\boldsymbol r',\boldsymbol r'',\boldsymbol r'''\right)&=\det\begin{bmatrix}a\sinh t&a\cosh t&b\\a\cosh t&a\sinh t&0\\a\sinh t&a\cosh t&0\end{bmatrix}=a^{2}b
\end{aligned}
$$

故

$$
\boxed{\kappa=\frac{a\sqrt{a^{2}+b^{2}\cosh 2t}}{\left(a^{2}\cosh 2t+b^{2}\right)^{3/2}},\quad
\tau=\frac{b}{a^{2}+b^{2}\cosh 2t}}\quad\boxed{\sigma_\omega\sigma}
$$

（3）$\boldsymbol r\left(t\right)=\left(a\left(1-\sin t\right),a\left(1-\cos t\right),bt\right)$（$a>0$）。

$$
\begin{aligned}
\boldsymbol r'&=\left(-a\cos t,a\sin t,b\right)\\
v^{2}&=a^{2}+b^{2}=:c^{2}\\
\boldsymbol r''&=\left(a\sin t,a\cos t,0\right)\\
\boldsymbol r'''&=\left(a\cos t,-a\sin t,0\right)\\
\boldsymbol r'\times \boldsymbol r''&=\left(-ab\cos t,ab\sin t,-a^{2}\right)\\
w^{2}&=a^{2}c^{2}\\
w&=ac\\
\left(\boldsymbol r',\boldsymbol r'',\boldsymbol r'''\right)&=\left\langle\left(-ab\cos t,ab\sin t,-a^{2}\right),\right.\\
&\quad\left.\left(a\cos t,-a\sin t,0\right)\right\rangle\\
&=-a^{2}b
\end{aligned}
$$

故

$$
\boxed{\kappa=\frac{a}{a^{2}+b^{2}},\quad\tau=-\frac{b}{a^{2}+b^{2}}}\quad\boxed{\sigma_\omega\sigma}
$$

---

## 5

球面曲线为像集落在 $\mathbb R^3$ 中某个球面上的曲线。

（1）球面曲线的曲率一定大于等于 $\frac1{r}$，其中 $r$ 为曲线所在球面的半径。

（2）*球面曲线的刻画*。证明：满足条件

$$
\left(\frac{1}{\kappa}\right)^2+\left[\frac{1}{\tau}\frac{d}{ds}\left(\frac{1}{\kappa}\right)\right]^2=\text{常数}
$$

的曲线，或者是球面曲线，或者 $\kappa$ 是常数。

### 解答

以下均设 $\boldsymbol\gamma=\boldsymbol\gamma(s)$ 以弧长为参数，且 $\kappa,\tau$ 处处非零，即分母 $\frac1\kappa,\frac1\tau$ 有意义。

**（1）** 设 $\boldsymbol\gamma$ 落在半径为 $r$ 的球面上。平移球心至原点，则 $\|\boldsymbol\gamma\|^{2}\equiv r^{2}$。由**球面曲线判定**命题的证明中对 $\langle\boldsymbol\gamma,\boldsymbol T\rangle\equiv0$、$\langle\boldsymbol\gamma,\boldsymbol N\rangle=-\frac1\kappa$、$\langle\boldsymbol\gamma,\boldsymbol B\rangle$ 的逐次求导，得分解

$$
\begin{aligned}
\boldsymbol\gamma&=-\frac1\kappa\boldsymbol N-\frac1\tau\left(\frac1\kappa\right)'\boldsymbol B\\
\|\boldsymbol\gamma\|^{2}&=\left(\frac1\kappa\right)^{2}+\left(\frac1\tau\left(\frac1\kappa\right)'\right)^{2}=r^{2}
\end{aligned}
$$

因 $\boldsymbol N,\boldsymbol B$ 为单位正交向量，故

$$
\begin{aligned}
&&r^{2}&\ge\left(\frac1\kappa\right)^{2}\\
\Rightarrow&&\frac1\kappa&\le r\\
\Rightarrow&&&\kern-0.9em\boxed{\kappa\ge\frac1r}\quad\boxed{\sigma_\omega\sigma}
\end{aligned}
$$

**（2）** 设

$$
\left(\frac1\kappa\right)^{2}+\left[\frac1\tau\frac{\mathrm d}{\mathrm ds}\left(\frac1\kappa\right)\right]^{2}=\text{常数}
$$

记 $\varphi:=\frac1\kappa$、$\psi:=\frac1\tau\varphi'$，则条件为 $\varphi^{2}+\psi^{2}=\text{常数}$。

**情形 A：$\varphi'$ 不恒为零。** 则存在子区间上 $\varphi'\ne0$。定义

$$
\widetilde{\boldsymbol\gamma}:=\boldsymbol\gamma+\frac1\kappa\boldsymbol N+\frac1\tau\left(\frac1\kappa\right)'\boldsymbol B
=\boldsymbol\gamma+\varphi\boldsymbol N+\psi\boldsymbol B
$$

由弗雷内方程 $\dot{\boldsymbol N}=-\kappa\boldsymbol T+\tau\boldsymbol B$、$\dot{\boldsymbol B}=-\tau\boldsymbol N$ 求导：

$$
\begin{aligned}
\widetilde{\boldsymbol\gamma}'
&=\boldsymbol T+\varphi'\boldsymbol N+\varphi\dot{\boldsymbol N}+\psi'\boldsymbol B+\psi\dot{\boldsymbol B}\\
&=\boldsymbol T+\varphi'\boldsymbol N+\varphi(-\kappa\boldsymbol T+\tau\boldsymbol B)+\psi'\boldsymbol B+\psi(-\tau\boldsymbol N)\\
&=(1-\varphi\kappa)\boldsymbol T+(\varphi'-\tau\psi)\boldsymbol N+(\tau\varphi+\psi')\boldsymbol B
\end{aligned}
$$

由 $\varphi=\frac1\kappa$ 得 $1-\varphi\kappa=0$，$\varphi'-\tau\psi=\varphi'-\tau\cdot\frac{\varphi'}{\tau}=0$。又对条件求导：

$$
\begin{aligned}
&&2\varphi\varphi'+2\psi\psi'&=0\\
\Rightarrow&&
\varphi\varphi'+\psi\psi'&=0
\end{aligned}
$$

在 $\varphi'\ne0$ 处除以 $\varphi'$，并代入 $\psi=\frac{\varphi'}{\tau}$，得

$$
\begin{aligned}
&&\varphi+\frac{\psi'}{\tau}&=0\\
\Rightarrow&&
\psi'&=-\tau\varphi\\
\Rightarrow&&
\tau\varphi+\psi'&=0
\end{aligned}
$$

故 $\widetilde{\boldsymbol\gamma}'=\boldsymbol 0$，$\widetilde{\boldsymbol\gamma}$ 为常向量。于是

$$
\|\boldsymbol\gamma-\widetilde{\boldsymbol\gamma}\|^{2}
=\|\varphi\boldsymbol N+\psi\boldsymbol B\|^{2}
=\varphi^{2}+\psi^{2}=\text{常数}>0
$$

故 $\boldsymbol\gamma$ 落在以 $\widetilde{\boldsymbol\gamma}$ 为球心的球面上，是**球面曲线**。

**情形 B：$\varphi'\equiv0$，即 $\left(\frac1\kappa\right)'\equiv0$。** 则 $\frac1\kappa$ 为常数，故

$$
\kappa\equiv\text{常数}
$$

综上，满足该条件的曲线，或者**落在球面上**（情形 A），或者 **$\kappa$ 为常数**（情形 B）。$\boxed{\sigma_\omega\sigma}$

---

## 6

### 8

设平面正则曲线 $C:\boldsymbol r=\boldsymbol r(t)$ 不过 $P_0$ 点，$\boldsymbol r(t_0)$ 是 $C$ 与 $P_0$ 距离最近的点，证明：向量 $\boldsymbol r(t_0)-P_0$ 与 $\boldsymbol r'(t_0)$ 垂直。

### 解答

考虑函数

$$
f(t):=\|\boldsymbol r(t)-P_0\|^{2}=\langle\boldsymbol r(t)-P_0,\boldsymbol r(t)-P_0\rangle
$$

由第 1 题（1），对 $\langle\boldsymbol a,\boldsymbol a\rangle$ 的求导规则有

$$
f'(t)=\frac{\mathrm d}{\mathrm dt}\|\boldsymbol r(t)-P_0\|^{2}
=2\langle\boldsymbol r(t)-P_0,\boldsymbol r'(t)\rangle
$$

因 $\boldsymbol r(t_0)$ 是 $C$ 上与 $P_0$ 距离最近的点，$f$ 在 $t_0$ 处取得最小值；又 $C$ 不过 $P_0$，故 $\boldsymbol r(t_0)\ne P_0$，最小值点 $t_0$ 是 $t$ 区间内部的点，$f$ 在 $t_0$ 处取极值，故 $f'(t_0)=0$。于是

$$
0=f'(t_0)=2\langle\boldsymbol r(t_0)-P_0,\boldsymbol r'(t_0)\rangle
$$

即 $\langle\boldsymbol r(t_0)-P_0,\boldsymbol r'(t_0)\rangle=0$。故向量 **$\boldsymbol r(t_0)-P_0$ 与 $\boldsymbol r'(t_0)$ 垂直**。$\boxed{\sigma_\omega\sigma}$

---

### 9

（1）设 $E^3$ 的曲线 $C$ 的所有切线过一个定点，证明：$C$ 是直线；

（2）证明：所有主法线过定点的曲线是圆。

### 解答

设 $\boldsymbol\gamma=\boldsymbol\gamma(s)$ 以弧长为参数。平移坐标使定点为原点。

**（1）** 每条切线都过原点，即曲线点 $\boldsymbol\gamma(s)$ 落在过原点的直线 $\mathrm{span}\{\boldsymbol T(s)\}$ 上，故存在数量函数 $\lambda(s)$ 使

$$
\boldsymbol\gamma(s)=\lambda(s)\boldsymbol T(s)
$$

依据 $\dot{\boldsymbol\gamma}=\boldsymbol T$，$\dot{\boldsymbol T}=\kappa\boldsymbol N$，对 $s$ 求导：

$$
\boldsymbol T=\dot{\boldsymbol\gamma}=\lambda'\boldsymbol T+\lambda\dot{\boldsymbol T}
=\lambda'\boldsymbol T+\lambda\kappa\boldsymbol N
$$

若某开区间上 $\kappa\ne0$，则 $\boldsymbol T,\boldsymbol N$ 线性无关，比较系数得 $\lambda'=1$ 且 $\lambda\kappa=0$。由 $\kappa\ne0$ 得 $\lambda=0$，进而 $\lambda'=0\ne1$，矛盾。故在整个区间上 $\kappa\equiv0$，即 $\dot{\boldsymbol T}\equiv\boldsymbol 0$。由 **$\dot{\boldsymbol T}\equiv\boldsymbol 0$ 当且仅当曲线是直线段**，曲线 $C$ **是直线**。$\boxed{\sigma_\omega\sigma}$

**（2）** 设 $\kappa\ne0$ 处处成立（否则主法线无定义）。每条主法线都过原点，即 $\boldsymbol\gamma(s)$ 落在过原点的直线 $\mathrm{span}\{\boldsymbol N(s)\}$ 上，故存在数量函数 $\lambda(s)$ 使

$$
\boldsymbol\gamma(s)=\lambda(s)\boldsymbol N(s)
$$

对 $s$ 求导（$\dot{\boldsymbol\gamma}=\boldsymbol T$，$\dot{\boldsymbol N}=-\kappa\boldsymbol T+\tau\boldsymbol B$）：

$$
\boldsymbol T=\dot{\boldsymbol\gamma}=\lambda'\boldsymbol N+\lambda\dot{\boldsymbol N}
=\lambda'\boldsymbol N+\lambda(-\kappa\boldsymbol T+\tau\boldsymbol B)
=-\lambda\kappa\boldsymbol T+\lambda'\boldsymbol N+\lambda\tau\boldsymbol B
$$

$\{\boldsymbol T,\boldsymbol N,\boldsymbol B\}$ 为标准正交基，比较系数：

$$
1=-\lambda\kappa,\quad 0=\lambda',\quad 0=\lambda\tau
$$

由 $0=\lambda'$ 得 $\lambda$ 为常数；由 $1=-\lambda\kappa\ne0$ 知 $\lambda\ne0$，再由 $\lambda\tau=0$ 得 $\tau\equiv0$。于是由 **$\tau\equiv0$ 当且仅当曲线是平面曲线**，$\boldsymbol\gamma$ 是平面曲线；又 $\lambda$ 为常数，故

$$
\|\boldsymbol\gamma\|=\|\lambda\boldsymbol N\|=|\lambda|=\text{常数}
$$

即曲线到原点的距离恒定。落在平面内且到定点距离恒定的曲线是**以原点为圆心、半径 $|\lambda|=\frac1\kappa$ 的圆**。$\boxed{\sigma_\omega\sigma}$

---

### 10

设 $T(\boldsymbol X)=X\boldsymbol T+P$ 是 $E^3$ 的一个合同（等距）变换，$\det \boldsymbol T=-1$。$\boldsymbol r(t)$ 是 $E^3$ 的正则曲线，求曲线 $\tilde{\boldsymbol r}=T\circ \boldsymbol r$ 与曲线 $\boldsymbol r$ 的弧长参数、曲率、挠率间的关系。

### 解答

设 $\boldsymbol T=\boldsymbol A$（正交矩阵、$\det\boldsymbol A=-1$，反向等距），则 $\tilde{\boldsymbol r}(t)=\boldsymbol A\boldsymbol r(t)+P$。

**弧长参数**。由正交性 $\boldsymbol A^{\top}\boldsymbol A=I_3$：

$$
|\tilde{\boldsymbol r}'|=|\boldsymbol A\boldsymbol r'|
=\sqrt{\langle\boldsymbol A\boldsymbol r',\boldsymbol A\boldsymbol r'\rangle}
=\sqrt{\langle\boldsymbol r',\boldsymbol r'\rangle}=|\boldsymbol r'|
$$

故 $\tilde s(t)=\int|\tilde{\boldsymbol r}'|\mathrm dt=\int|\boldsymbol r'|\mathrm dt=s(t)$（只差常数）。因此 $\boldsymbol r$ 的弧长参数 $s$ 仍是 $\tilde{\boldsymbol r}$ 的弧长参数，**弧长参数化不变**。

**曲率**。以 $s$ 为共同弧长参数，$\tilde{\boldsymbol T}=\dot{\tilde{\boldsymbol r}}=\boldsymbol A\dot{\boldsymbol r}=\boldsymbol A\boldsymbol T$。空间曲率 $\kappa=\|\dot{\boldsymbol T}\|$，由正交性：

$$
\tilde\kappa=\|\dot{\tilde{\boldsymbol T}}\|=\|\boldsymbol A\dot{\boldsymbol T}\|
=\sqrt{\langle\boldsymbol A\dot{\boldsymbol T},\boldsymbol A\dot{\boldsymbol T}\rangle}=\|\dot{\boldsymbol T}\|=\kappa
$$

故**曲率不变** $\tilde\kappa=\kappa$。

**挠率**。由**一般参数下的挠率公式** $\tau=\frac{(\boldsymbol r',\boldsymbol r'',\boldsymbol r''')}{w^{2}}$，

$$
\begin{aligned}
\tilde\tau
&=\frac{(\tilde{\boldsymbol r}',\tilde{\boldsymbol r}'',\tilde{\boldsymbol r}''')}{\tilde w^{2}}
=\frac{\det(\boldsymbol A\boldsymbol r',\boldsymbol A\boldsymbol r'',\boldsymbol A\boldsymbol r''')}{w^{2}}\\
&=\frac{\det(\boldsymbol A)\det(\boldsymbol r',\boldsymbol r'',\boldsymbol r''')}{w^{2}}
=-\frac{(\boldsymbol r',\boldsymbol r'',\boldsymbol r''')}{w^{2}}=-\tau
\end{aligned}
$$

其中用到 $\det\boldsymbol A=-1$。故**挠率变号** $\tilde\tau=-\tau$。

综上：

$$
\boxed{\tilde s=s,\quad \tilde\kappa=\kappa,\quad \tilde\tau=-\tau}\quad\boxed{\sigma_\omega\sigma}
$$
