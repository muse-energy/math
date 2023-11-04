# Cauchy-Riemannの方程式

複素数は二つの実数の組として表されるので、複素関数は、二つの実数を引数として二つの実数を返すような関数だと思うこともできる。実二変数関数に対しては、偏微分や全微分を用いて局所的なふるまいを調べることができるのだった。このページでは、複素微分可能性が偏微分を用いてどのように記述できるかを説明する。

## 複素微分と偏微分
実数 $x$, $y$ を用いて、複素数 $z$ を $z= x + iy$ と表すことにする。

$\Omega \subset \mathbb{C}$ を領域とする。複素関数 $f: \Omega \to \mathbb{C}$ を、ふたつの実関数 $u, v: \Omega \to \mathbb{R}$ を用いて
$$f(x+iy) = u(x,y) + iv(x,y) $$
と表すことができる。

!!! example "例"
    $f(z) = z^2$ のときは、

    $$ \begin{align*}f(x+iy) &= (x+iy)^2 \\
    &= (x^2 - y^2) + 2xyi
    \end{align*}$$
    
    より、$u(x,y) = x^2 - y^2$, $v(x,y) = 2xy$ である。

この書き方のもとで、$f$ の複素微分を、$u, v$ の偏微分を用いて記述しよう。

まず、$z \in \Omega$ に実軸方向から近づけることを考える。このとき、

$$ \begin{align*}\lim_{h \in \mathbb{R}, h \to 0} \frac{f(z+h) - f(z)}{h} &= \lim_{h \to 0} \frac{u(x+h, y) + i v(x+h, y) - u(x,y) - i v(x,y)}{h}\\
&= \lim_{h \to 0} \left(\frac{u(x+h, y) - u(x,y)}{h} + i  \frac{v(x+h, y) - v(x,y)}{h}\right)\end{align*} $$

と計算できる。複素数としての収束は、実部と虚部がそれぞれ収束することと同値であるので、この極限が存在することは、
$$\lim_{h \to 0} \frac{u(x+h, y) - u(x,y)}{h} = \frac{\partial u}{\partial x}(x,y) $$
$$\lim_{h \to 0} \frac{v(x+h, y) - v(x,y)}{h} = \frac{\partial v}{\partial x}(x,y) $$
がそれぞれ存在することと同値である。すると、偏微分を用いて、
$$\lim_{h \in \mathbb{R}, h \to 0} \frac{f(z+h) - f(z)}{h} = \frac{\partial u}{\partial x}(x,y) + i\frac{\partial v}{\partial x}(x,y) $$
と書くことができる。

次に、$z \in \Omega$に虚軸方向から近づけることを考える。このときは、

$$ \begin{align*}\lim_{h \in \mathbb{R}, h \to 0} \frac{f(z+ih) - f(z)}{ih} &= \lim_{h \to 0} \frac{u(x, y+h) + i v(x, y+h) - u(x,y) - i v(x,y)}{ih}\\
&= -i\lim_{h \to 0} \left(\frac{u(x, y+h) - u(x,y)}{h} +  \frac{v(x, y+h) - v(x,y)}{h}\right)\end{align*} $$

であるから、この極限の存在は、
$$\lim_{h \to 0} \frac{u(x, y+h) - u(x,y)}{h} = \frac{\partial u}{\partial y}(x,y) $$
$$\lim_{h \to 0} \frac{v(x, y+h) - v(x,y)}{h} = \frac{\partial v}{\partial y}(x,y) $$
がそれぞれ存在することと同値である。これより、
$$\lim_{h \in \mathbb{R}, h \to 0} \frac{f(z+ih) - f(z)}{ih} = -i\frac{\partial u}{\partial y}(x,y) + \frac{\partial v}{\partial y}(x,y) $$
と書くことができる。

$f$ が $z$ において複素微分可能であるとすると、これらの極限は一致することになる。したがって、このとき、
$$\frac{\partial u}{\partial x}(x,y) + i\frac{\partial v}{\partial x}(x,y) = -i\frac{\partial u}{\partial y}(x,y) + \frac{\partial v}{\partial y}(x,y) $$
を得る。実部と虚部をそれぞれ比較して、

$$\left\{\begin{align*}\frac{\partial u}{\partial x}(x,y) &= \frac{\partial v}{\partial y}(x,y) \\
\frac{\partial u}{\partial y}(x,y) &= -\frac{\partial v}{\partial x}(x,y) \end{align*} \right.$$

を得る。この2本の方程式を合わせて **Cauchy-Riemannの方程式** と呼ぶ。

!!! example "例"
    先ほど挙げた $f(z)=z^2$ の場合、$u(x,y) = x^2-y^2$, $v(x,y) = 2xy$ であった。これらの関数の偏微分を計算すると、
    
    $$ \begin{align*}
    \frac{\partial u}{\partial x}(x,y) = 2x, \,\,\,\,& \frac{\partial u}{\partial y}(x,y) = -2y,  \\
    \frac{\partial v}{\partial x}(x,y) = 2y, \,\,\,\,& \frac{\partial v}{\partial y}(x,y) = 2x  
    \end{align*} $$
    
    となり、Cauchy-Riemannの方程式を満たすことが確認できる。

## 複素微分可能性とCauchy-Riemannの方程式 

以上の議論では、複素微分可能であればCauchy-Riemannの方程式を満たすことを確かめたが、$u, v$ が全微分可能であるときに逆も成り立つことを示す。

!!! proposition "命題"
    $\Omega \subset \mathbb{C}$ を領域とする。$f: \Omega \to \mathbb{C}$ とする。$u, v: \Omega \to \mathbb{R}$として、$f= u + iv$ と書く。 $z \in \Omega$ として、$x, y \in \mathbb{R}$ に対して $z = x+iy$ と書く。このとき、以下は同値である：
    
    (1) $f$ は $z$ において複素微分可能である。
    
    (2) $u ,v$ は $(x,y)$ において全微分可能で、Cauchy-Riemannの方程式を満たす。

**証明**
(1)$\Rightarrow$(2) $f$ は $z$ において複素微分可能なので、ある複素数 $A$ が存在して、
$$f(w) = f(z) + A (z-w) + r(w) $$
と書いたとき、
$$\lim_{w \to z} \frac{|r(w)|}{|w-z|} = 0 $$
となるようにできる。$u, v$ の全微分可能性を示すために、この式を実関数としての等式に書き直そう。

$z = x+iy$, $w = \xi + i \eta$, $A = \alpha + i\beta$ とおく。このとき、

$$\begin{align*}
&f(z) + A(z-w) + r(w) \\
= \,& (u(x, y) +iv(x,y)) + (\alpha + i \beta)((\xi + i\eta) - (x + iy)) + r(\xi + i\eta)\\
= \,& (u(x, y) +iv(x,y)) + (\alpha + i \beta)((\xi - x) + i (\eta - y)) + r(\xi + i\eta)\\
= \,& u(x,y) + \alpha (\xi-x) - \beta(\eta - y) + \mathrm{Re}\, r(\xi + i\eta)\\
& + i (v(x,y) + \beta(\xi-x) + \alpha(\eta - y) + \mathrm{Im}\, r(\xi + i\eta))\end{align*} $$

と書ける。これが $f(w) = u(\xi, \eta) + iv(\xi, \eta)$ と一致することから、実部と虚部をそれぞれ比較して、

$$\begin{align}
u(\xi, \eta) &= u(x,y) + \alpha (\xi-x) - \beta(\eta - y) + \mathrm{Re}\, r(\xi + i\eta)\\
v(\xi, \eta) &= v(x,y) + \beta(\xi-x) + \alpha(\eta - y) + \mathrm{Im}\, r(\xi + i\eta)
\end{align} $$


を得る。一つ目の式の最後の項は、$(\xi, \eta) \to (x,y)$ のとき

$$\frac{|\mathrm{Re}\, r(\xi + i\eta)|}{\|(\xi-x, \eta-y)\|} = \frac{|\mathrm{Re}\,r(w)|}{|w-z|} \leq \frac{|r(w)|}{|w-z|} \to 0 $$

となる。したがって、$u$ は $(x,y)$ において全微分可能である。同様に、$v$ も $(x,y)$ において全微分可能である。

$u, v$ がCauchy-Riemannの方程式を満たすことはこの命題の前でやった通りであるが、上式 $(1)$, $(2)$ からも、
$$\frac{\partial u}{\partial x}(x,y) = \frac{\partial v}{\partial y}(x,y) = \alpha $$
$$ - \frac{\partial u}{\partial y}(x,y) = \frac{\partial v}{\partial x}(x,y) = \beta $$
が成り立つことがわかる。

(2)$\Rightarrow$(1) $u$, $v$ が $(x, y)$ において全微分可能かつCauchy-Riemannの方程式を満たすことから、ある実数 $\alpha$, $\beta$ が存在して、

$$\begin{align}
u(\xi, \eta) &= u(x,y) + \alpha (\xi-x) - \beta(\eta - y) + r_1(\xi, \eta)\\
v(\xi, \eta) &= v(x,y) + \beta(\xi-x) + \alpha(\eta - y) + r_2(\xi,\eta)
\end{align} $$

と書いたときに、$r_1$, $r_2$ が

$$\lim_{(\xi, \eta) \to (x,y)} \frac{|r_1(\xi,\eta)|}{ \|(\xi-x, \eta-y)\|} = 0, \,\,\,\,\lim_{(\xi, \eta) \to (x,y)} \frac{|r_2(\xi,\eta)|}{ \|(\xi-x, \eta-y)\|} = 0 $$

をみたすようにできる。 $(3)$ 式に $(4)$ 式の $i$ 倍を足すと、

$$\begin{align*} u(\xi, \eta) + i v(\xi, \eta) =&\, u(x,y) + i v (x,y) \\
 &  + \alpha((\xi-x) + i (\eta - y)) + \beta(i(\xi-x) - (\eta-y))\\
 & + r_1(\xi,\eta) + ir_2(\xi,\eta)\end{align*} $$

を得る。$r(w) := r_1(\xi, \eta) + i r_2(\xi, \eta)$ とおいて整理すると、

$$\begin{align*}f(w)&=f(z) + \alpha \cdot (w-z) + \beta \cdot i(w-z) + r(w)\\
&= f(z) + (\alpha + i\beta)(w-z) + r(w) \end{align*} $$

となる。あとは、$r(w)$ の項が $o(|w-z|)$ のオーダーであることを見ればよいが、

$$\lim_{w \to z} \frac{|r(w)|}{|w-z|} \leq \lim_{ (\xi,\eta) \to (x, y) } \left(\frac{|r_1(\xi, \eta)|}{\|(\xi-x, \eta - y)\|} + \frac{|r_2(\xi, \eta)|}{\|(\xi-x, \eta - y)\|}\right) = 0 $$

よりok。$\square$

## まとめ
!!! summary "まとめ"
    - 複素微分可能性から、Cauchy-Riemannの方程式を導いた。
    - 複素微分可能であることと、全微分可能かつCauchy-Riemannの方程式をみたすことの同値性を示した。