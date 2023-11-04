# 指数関数と三角関数

正則関数の例として、複素数に対して指数関数・三角関数を定義する。これらの関数の定義にはいろいろな流儀があると思うが、ここでは実数に対する指数関数・三角関数の定義や性質をすでに知っているものとして、それを利用して複素数に対する定義を行うことにする。

## 指数関数

!!! definition "定義(指数関数)"
    複素数 $z = x + iy$ に対して、
    $$\exp(z) := e^x (\cos y + i \sin y) $$
    とおく。

$y = 0$ であれば右辺は
$$e^x (\cos y + i \sin y) = e^x (1 + i \cdot 0) = e^x $$
だから、実数に対してはもともと知っている指数関数と一致している。

!!! remark "注意"
    $\exp(z)$ のことを $e^z$ とも書く。ここでは、新しく定義した関数であることを強調するために別の記号を用いた。

この定義だけ見てもなぜこの定義なのかは分かりづらいが、このように定義しておくと以下に見るように様々な性質が成り立つ。

### 指数法則
!!! proposition "命題"
    $z, w \in \mathbb{C}$に対して、$\exp(z+w) = \exp(z) \cdot \exp(w)$ である。

**証明**
$z=x+iy$, $w=\xi + i \eta$ とおく。計算すると、

$$\begin{align*}\exp(z+w) &= e^{x+\xi} (\cos(y + \eta) + i \sin(y + \eta))\\
&= e^{x+\xi}(\cos y \cos \eta - \sin y \sin \eta + i \sin y \cos \eta + i \cos y \sin \eta)\\
&= e^x e^{\xi}(\cos y + i \sin y)(\cos \eta + i \sin \eta)\\
&= \exp(z) \exp(w)\end{align*}$$

であることがわかる。$\square$

### $\exp$ の正則性
!!! proposition "命題"
    $\exp$ は $\mathbb{C}$ 上の正則関数である。

**証明**
$\exp$ は実部も虚部も $C^\infty$ 級(すべての偏導関数が存在して連続)で、特に全微分可能である。(このあたりの事情はそのうちどこかで…)

Cauchy-Riemannの方程式を確かめる。$\exp(z) = u(x, y) + iv(x,y)$ と書くと、
$$u(x, y) = e^x \cos y, $$
$$v(x, y) = e^x \sin y $$
である。
それぞれの偏微分を計算すると、
$$\frac{\partial u}{\partial x} = e^x \cos y, \,\,\,\,\frac{\partial u}{\partial y} = -e^x \sin y $$
$$\frac{\partial v}{\partial x} = e^x \sin y, \,\,\,\,\frac{\partial v}{\partial y} = e^x \cos y $$
だから、
$$\frac{\partial u}{\partial x} = \frac{\partial v}{\partial y},\,\,\,\, \frac{\partial u}{\partial y} = -\frac{\partial v}{\partial x} $$
となる。$\square$

複素微分を計算してみよう。正則であることをすでに確かめたので、どの向きに微分を計算してもよく、例えば $x$ 軸方向から近づけることを考えると、

$$\begin{align*}\exp'(z) &= \frac{\partial}{\partial x}(\exp(z))\\
&= \frac{\partial}{\partial x}(e^x (\cos y + i \sin y)) \\
&= e^x(\cos y + i \sin y) = \exp(z)\end{align*}$$

を得る。(この説明ちょっと微妙な気がしてきたのでもう少し考える)