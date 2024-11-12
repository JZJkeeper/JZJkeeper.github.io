



球谐函数（Spherical Harmonics）是通过在球坐标下求解三维拉普拉斯方程（Laplace's Equation）得到的。下面将详细展示这一计算过程，每一步都尽量清晰。

### 1. 三维拉普拉斯方程

三维拉普拉斯方程在笛卡尔坐标下表示为：

$\nabla^2 \Phi = 0$

其中，$\nabla^2$ 是拉普拉斯算子，$\Phi$ 是待求解的函数。

### 2. 转换为球坐标

在球坐标下（$r, \theta, \phi$），拉普拉斯算子可以表示为：

$\nabla^2 \Phi = \frac{1}{r^2} \frac{\partial}{\partial r} \left( r^2 \frac{\partial \Phi}{\partial r} \right) + \frac{1}{r^2 \sin^2 \theta} \frac{\partial^2 \Phi}{\partial \phi^2} + \frac{1}{r^2 \sin \theta} \frac{\partial}{\partial \theta} \left( \sin \theta \frac{\partial \Phi}{\partial \theta} \right)$

### 3. 分离变量

假设 $\Phi(r, \theta, \phi)$ 可以分离为径向函数 $R(r)$ 和角向函数 $Y(\theta, \phi)$ 的乘积，即：

$\Phi(r, \theta, \phi) = R(r) Y(\theta, \phi)$

### 4. 代入拉普拉斯方程

将 $\Phi(r, \theta, \phi)$ 代入拉普拉斯方程，得到：

$\frac{1}{r^2} \frac{d}{dr} \left( r^2 \frac{dR}{dr} \right) + \frac{1}{r^2 \sin^2 \theta} \frac{\partial^2 Y}{\partial \phi^2} + \frac{1}{r^2 \sin \theta} \frac{\partial}{\partial \theta} \left( \sin \theta \frac{\partial Y}{\partial \theta} \right) = 0$

### 5. 分离方程

通过乘以 $r^2$ 并重新整理，可以将方程分离为两部分：

$\frac{d}{dr} \left( r^2 \frac{dR}{dr} \right) = -\lambda r^2$

$\frac{1}{\sin^2 \theta} \frac{\partial^2 Y}{\partial \phi^2} + \frac{1}{\sin \theta} \frac{\partial}{\partial \theta} \left( \sin \theta \frac{\partial Y}{\partial \theta} \right) = \lambda$

其中，$\lambda$ 是一个分离常数。

### 6. 求解径向方程

径向方程可以进一步简化为：

$r^2 \frac{d^2R}{dr^2} + 2r \frac{dR}{dr} + \lambda r^2  = 0$

这是一个二阶常微分方程，其解的形式取决于 $\lambda$ 的值。通常，我们设 $\lambda = l(l+1)$，其中 $l$ 是一个非负整数，这样方程就有解：

$R(r) = A r^l + \frac{B}{r^{l+1}}$

在物理问题中，通常要求解在原点有限且随 $r$ 趋于无穷大时趋于零的解，因此 $B$ 必须为零，且 $A$ 可以归一化。

### 7. 求解角向方程

角向方程为：

$\frac{1}{\sin^2 \theta} \frac{\partial^2 Y}{\partial \phi^2} + \frac{1}{\sin \theta} \frac{\partial}{\partial \theta} \left( \sin \theta \frac{\partial Y}{\partial \theta} \right) = l(l+1) Y$

通过进一步分离变量 $Y(\theta, \phi) = \Theta(\theta) \Phi(\phi)$，并代入上式，可以得到两个方程：

$\frac{d^2 \Phi}{d\phi^2} = m^2 \Phi$

$\frac{1}{\sin \theta} \frac{d}{d\theta} \left( \sin \theta \frac{d\Theta}{d\theta} \right) + \left[ l(l+1) - \frac{m^2}{\sin^2 \theta} \right] \Theta = 0$

其中，$m$ 是一个整数，且 $|m| \leq l$。

### 8. 求解角向方程的 $\Phi(\phi)$ 部分

$\Phi(\phi) = e^{im\phi}$

### 9. 求解角向方程的 $\Theta(\theta)$ 部分
$\frac{1}{\sin \theta} \frac{d}{d \theta} \left( \sin \theta \frac{d \Theta}{d \theta} \right) + \left( l(l+1) - \frac{m^2}{\sin^2 \theta} \right) \Theta = 0.$
通过变换和进一步求解，可以得到 $\Theta(\theta)$ 的解为勒让德多项式（Associated Legendre Polynomials）的形式。

### 10. 综合解

最终，球谐函数 $Y_{lm}(\theta, \phi)$ 可以表示为：

$Y_{lm}(\theta, \phi) = \sqrt{\frac{(2l+1)(l-m)!}{(l+m)!}} P_l^m(\cos \theta) e^{im\phi}$

其中，$P_l^m(\cos \theta)$ 是勒让德多项式。

下面我们列出几个球谐函数：
$\begin{aligned}&Y_{0}^{0}=\sqrt{\frac{1}{4\pi}}\\&Y_{-1}^{1}=\sqrt{\frac{4}{8\pi}}\sin\theta e^{-i\phi},Y_{0}^{1}=\sqrt{\frac{4}{8\pi}}\cos\theta,Y_{1}^{1}=-\sqrt{\frac{4}{8\pi}}\sin\theta e^{i\phi}\\&Y_{-2}^{2}=\frac{1}{4}\sqrt{\frac{15}{2\pi}}\sin^{2}\theta e^{-2i\phi},Y_{-1}^{2}=\frac{1}{2}\sqrt{\frac{15}{2\pi}}\sin\theta\cos\theta e^{-i\phi},Y_{0}^{2}=\frac{1}{4}\sqrt{\frac{5}{\pi}}(3\cos^{2}\theta-1),\\&Y_{1}^{2}=-Y_{-1}^{2}{}^{*},Y_{2}^{2}=Y_{-2}^{2}{}^{*}\end{aligned}$
