# 指数関数と三角関数

正則関数の例として、複素数に対して指数関数・三角関数を定義する。これらの関数の定義にはいろいろな流儀があると思うが、ここでは実数に対する指数関数・三角関数の定義や性質をすでに知っているものとして、それを利用して複素数に対する定義を行うことにする。

## 指数関数

!!! definition "定義(指数関数)"
    複素数 $z = x + iy$ に対して、
    $$\exp(z) := e^x (\cos y + i \sin y) $$
    とおく。$\exp(z)$ のことを $e^z$ とも書く。


$y = 0$ であれば右辺は
$$e^x (\cos y + i \sin y) = e^x (1 + i \cdot 0) = e^x $$
だから、実数に対してはもともと知っている指数関数と一致している。
    
この定義だけ見てもなぜこの定義なのかは分かりづらいが、このように定義しておくと以下に見るように様々な性質が成り立つ。

### 指数法則
!!! proposition "命題"
    (1) $z, w \in \mathbb{C}$に対して、$\exp(z+w) = \exp(z) \cdot \exp(w)$ である。

    (2) $z \in \mathbb{C}$ と $n \in \mathbb{N}$ に対して、$\exp(nz) = (\exp(z))^n$ である。

**証明**
(1) $z=x+iy$, $w=\xi + i \eta$ とおく。計算すると、

$$\begin{align*}\exp(z+w) &= e^{x+\xi} (\cos(y + \eta) + i \sin(y + \eta))\\
&= e^{x+\xi}(\cos y \cos \eta - \sin y \sin \eta + i \sin y \cos \eta + i \cos y \sin \eta)\\
&= e^x e^{\xi}(\cos y + i \sin y)(\cos \eta + i \sin \eta)\\
&= \exp(z) \exp(w)\end{align*}$$

であることがわかる。

(2) (自然数を何から始めることにするのかちゃんと考えていなかった。とりあえず $n=0$ から示す)

$n=0$ のときは、$\exp(0\cdot z) = 1 = \exp(z)^0$ なので成り立つ。

$n-1$ で正しいとすると、

$$\begin{align*}
\exp(nz) &= \exp((n-1)z + z)\\
&=\exp((n-1)z) \exp(z) &(←(1)より)\\
&=(\exp(z))^{n-1} \exp(z)\\
&=(\exp(z))^n
\end{align*} $$

となり、$n$でも成り立つ。
$\square$

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

## 三角関数
指数関数の定義で $x=0$ とおくと、**Eulerの公式**
$$\exp(iy) = \cos y + i\sin y $$
を得る。さらに、ここで $y$ を $-y$ で置き換えると、
$$\exp(-iy) = \cos y - i \sin y $$
となる。これらの式を組み合わせると、
$$\cos y = \frac{\exp(iy) + \exp(-iy)}{2}, $$
$$\sin y = \frac{\exp(iy) - \exp(-iy)}{2i} $$
という表示を得ることができる。これは $y$ が実数であるときの式だが、この式を元に次のように複素数に対する三角関数を定義する：
!!! definition "定義"
    複素数 $z$ に対して、
    $$\cos z = \frac{\exp(iz) + \exp(-iz)}{2}, $$
    $$\sin z = \frac{\exp(iz) - \exp(-iz)}{2i} $$
    と定める。

$\exp$ が正則関数だったこと(と、正則関数の和・差・積や合成も正則になること)から、$\cos$, $\sin$ も正則関数になる。
複素微分を計算すると、
$$(\cos z)' = \frac{i\exp(iz) + (-i)\exp(-iz)}{2} = \frac{-\exp(iz) +\exp(-iz)}{2i} = -\sin z, $$
$$(\sin z)' = \frac{i\exp(iz) - (-i)\exp(-iz)}{2i} = \frac{\exp(iz) +\exp(-iz)}{2} = \cos z $$
となる。これは、実数に対する三角関数の微分と一致している。

### 加法定理
三角関数の色々な性質も実数の場合と同様に成り立つものが多い。ここでは、例として加法定理を挙げる。

!!! proposition "命題"
    複素数 $z, w$ に対して、以下が成り立つ：
    $$\cos(z+w) = \cos z \cos w - \sin z \sin w, $$
    $$\sin(z+w) = \sin z \cos w + \cos z \sin w $$

証明は、定義をもとに $\exp$ に直して指数法則を適用することで行う。(後で書く/計算練習としてやってみてください！！)

## まとめ
!!! summary "まとめ"
    - 実数に対する指数関数・三角関数の定義を複素数まで拡張し、$\mathbb{C}$ 上の正則関数を得た。
    - 実数における性質と類似の性質を紹介した。