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
