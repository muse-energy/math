# Cauchyの積分公式

Cauchyの積分定理を活用することで、Cauchyの積分公式を得る。これは複素解析における最重要定理といってよいもので、正則関数の良い性質はすべてここから来ているといっても過言ではない。

!!! theorem "Cauchyの積分公式"
    $\Omega \subset \mathbb{R}^2$ を領域として、$C: [a, b] \to \Omega$ を区分的 $C^1$ 級曲線とする。
    $C$ は左回りの単純閉曲線であるとする。また、ある領域 $U \subset \Omega$ が存在して、その境界 $\partial U$ は$C$ (の像)と一致すると仮定する。このとき、$\Omega$ 上の $C^1$ 級正則関数 $f$ と$z \in U$ に対して、
    $$ f(z) = \frac{1}{2\pi i}\int_C \frac{f(\zeta)}{\zeta - z} d\zeta $$
    が成り立つ。

公式を眺めてみると、関数 $f$ の $z \in U$ における値が、$C$ すなわち $\partial U$ 上の積分だけで決まっているということがわかる。すなわち、$f$ の $U$ における挙動は、$U$の境界の値から完全に決定されてしまうわけである。「境界を見れば内部がわかる」というところに、正則関数の性質の良さが表れている。

**証明** $U_\epsilon := U\setminus \overline{\Delta(z, \epsilon)}$ とおく。すると、関数 $g(\zeta) := \displaystyle\frac{f(\zeta)}{\zeta - z}$ は $U_\epsilon$ 上正則である。
また、$\partial U_\epsilon = C \cup \partial \Delta(z, \epsilon)$ であるから、$U_\epsilon$ 上でCauchyの積分定理より、
$$ \int_C g(\zeta) d\zeta - \int_{\partial \Delta(z, \epsilon)} g(\zeta) d\zeta = 0 $$
が成り立つ。(内側の境界での積分は符号がマイナスになる)

2項目を計算しよう。

$$ \begin{align*}
\int_{\partial \Delta(z, \epsilon)} g(\zeta) d\zeta &= \int_{\theta = 0}^{2\pi} g(z + \epsilon e^{i\theta}) d(\epsilon e^{i\theta})\\
&= \int_{\theta = 0}^{2\pi} \frac{f(z + \epsilon e^{i\theta})}{z + \epsilon e^{i \theta} - z} \epsilon\cdot ie^{i \theta} d\theta\\
&= i \int_{\theta = 0}^{2\pi} f(z + \epsilon e^{i \theta}) d \theta
\end{align*} $$

$f$ の連続性から、被積分関数は $\epsilon \to 0$ のとき $\theta$ によらず一様に $f(z)$ に収束する。したがって、この積分は $\epsilon \to 0$ のとき
$$ i \int_{\theta = 0}^{2\pi} f(z) d \theta = 2\pi i f(z) $$
に収束する。

いま、
$$ \int_C g(\zeta) d\zeta = \int_{\partial \Delta(z, \epsilon)} g(\zeta) d\zeta$$
だったので、両辺で$\epsilon \to 0$ とすると、
$$ \int_C g(\zeta) d\zeta = 2 \pi i f(z) $$ 
を得る。整理すると、
$$ f(z) = \frac{1}{2 \pi i}\int_C g(\zeta) d \zeta = \frac{1}{2 \pi i}\int_C \frac{f(\zeta)}{\zeta - z} d\zeta$$
がわかる。□

## 微分係数版

Cauchyの積分定理の右辺に現れる被積分関数 $\displaystyle\frac{f(\zeta)}{\zeta - z}$ は、$\zeta$ を固定すると、$z$ の関数として $C$ (の像)の近傍で正則(かつ無限回微分可能)である。そこで、Cauchyの積分公式の右辺を $z$ で微分することを考えよう。細かい議論は後回しにして、積分と微分が入れ替えられると期待して計算してみると、

$$ \begin{align*}
f'(z) &= \frac{d}{dz} \left(\frac{1}{2\pi i}\int_C \frac{f(\zeta)}{\zeta - z} d\zeta \right)\\
&{\color{#CC3333} {}={}}\frac{1}{2\pi i}\int_C \frac{d}{dz} \left(\frac{f(\zeta)}{\zeta - z}  \right)d\zeta\\
&= \frac{1}{2\pi i}\int_C \frac{f(\zeta)}{(\zeta - z)^2} d\zeta
\end{align*} $$

を得る(赤い ${\color{#CC3333}=}$ は入れ替えられると期待して計算した箇所を示す)。もう一度 $z$ で微分してみると、
$$ f''(z) = \frac{2}{2 \pi i} \int_C \frac{f(\zeta)}{(\zeta - z)^3} d \zeta $$
$$ f^{(3)}(z) = \frac{6}{2 \pi i} \int_C \frac{f(\zeta)}{(\zeta - z)^4} d \zeta $$
$$ \vdots $$
と続き、結局、
$$ f^{(n)}(z) = \frac{n!}{2 \pi i} \int_C \frac{f(\zeta)}{(\zeta - z)^{n+1}} d \zeta $$
が得られる。あとは赤い ${\color{#CC3333}=}$ の部分をちゃんと示せば、正則関数に対して、その $n$ 階微分の公式が得られることになる。さらにいうと、最初 $f$ は $C^1$ 級としか仮定していなかったので、**$C^1$ 級正則関数は無限回複素微分可能である** という性質も得られる。

- 正則関数は $\partial f/\partial \overline{z} = 0$ を満たす(Cauchy-Riemann)というのも合わせると、結局、正則関数は $C^\infty$ 級であることもわかるっぽい。

**積分と微分が入れ替えられることの証明** 最初の計算について示す。$n=2$ 以降の計算については同様の議論を繰り返せばよい。

計算したい微分は、(係数は定数なので省くと)
$$ \frac{d}{dz} \left(\int_C \frac{f(\zeta)}{\zeta - z} d\zeta \right) $$
である。これを定義通りに書くと、
$$ \lim_{h \to 0} \frac{1}{h}\left(\int_C \frac{f(\zeta)}{\zeta - (z+h)} d\zeta - \int_C \frac{f(\zeta)}{\zeta - z} d\zeta\right) $$
である。極限の中身は、

$$ \begin{align*}
&\frac{1}{h}\int_C f(\zeta) \left(\frac{1}{\zeta - (z+h)} - \frac{1}{\zeta - z}\right)d\zeta \\
= &\frac{1}{h}\int_C f(\zeta) \frac{h}{(\zeta - (z+h))(\zeta - z)} d\zeta \\
= &\int_C f(\zeta) \frac{1}{(\zeta - (z+h))(\zeta - z)} d\zeta
\end{align*} $$

となる。あとはこれで $h \to 0$ とすることを考えればよい。収束先は
$$ \int_C f(\zeta) \frac{1}{(\zeta -z)^2} d\zeta $$
であってほしいので、差が0に行くことを確かめる。

(以下雑な議論。あとでもっと詳しく書く)
計算すると、
$$ 差 = \int_C f(\zeta) \frac{h}{(\zeta - (z+h))(\zeta -z)^2} d\zeta $$
とかそういう感じになるはず。$C$ はコンパクトなので、$f(\zeta)$や$\frac{1}{(\zeta-(z+h))(\zeta - z)^2}$には最大値がある…ということをちゃんと確かめると、
$$ |差| \leq M|h|\int_C|d\zeta| \to 0 $$
が言えるはず。


