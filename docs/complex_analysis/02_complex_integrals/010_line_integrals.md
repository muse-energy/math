# 複素線積分


$\mathbb{C}$ 内の曲線に沿って、正則関数を積分することを考える。
(なんか議論の順番が怪しくなるのでやっぱりまずは実解析の解説を書いたほうがいい気もするな～～)


## 実関数の線積分
まずは実関数の線積分を思い出そう。

!!! definition "定義"
    $\Omega \subset \mathbb{R}^2$ を領域として、$f, g: \Omega \to \mathbb{R}^2$ を関数とする。$C^1$ 級曲線 $C: [a,b] \to \Omega$ を、ふたつの関数 $p, q: [a,b] \to \mathbb{R}$ を用いて、
    $$C(t)=(p(t), q(t)) \,\,\,\,(a \leq t \leq b) $$
    と表す。$C$ に沿う **線積分** を、

    $$\begin{align*}
    \int_C f(x,y)dx := \int_a^b f(p(s), q(s)) \frac{dp}{dt}(s)\, ds\\
    \int_C g(x,y)dy := \int_a^b g(p(s), q(s)) \frac{dq}{dt}(s)\, ds
    \end{align*} $$

    <!--
    没定義：どれが読みやすい？
    $$\int_C (f(x,y)dx + g(x,y)dy) := \int_a^b \left(f\circ C(s) \cdot p'(s) + g \circ C(s) \cdot q'(s)\right) ds  $$
    $$\begin{align*}
    \int_C f(x,y)dx := \int_a^b f(p(s), q(s)) p'(s)\, ds\\
    \int_C g(x,y)dy := \int_a^b g(p(s), q(s)) q'(s)\, ds\\
    \end{align*}$$
    -->

    と定める。

!!! remark "積分可能性について"
    積分可能性をあまり気にせずに定義したが、もちろん右辺の積分ができない場合は線積分も定義されない。積分の流儀にもいろいろあるが、ここではとりあえずRiemann積分を採用することにする。

    $f$ や $g$ が $\Omega$ 上連続であれば、右辺が連続関数になるので、そのような場合は線積分はちゃんと定義できる(有界閉区間上の連続関数はRiemann積分可能である)。

!!! remark "Riemann和による定義"
    曲線を細かく分割して、分点を$(x_0, y_0), (x_1, y_1), \ldots, (x_N, y_N)$とおく。これを用いて、例えば
    $$\sum_{i=1}^N f(x_i,y_i)(x_i-x_{i-1}) $$
    という量を考えて、その極限として線積分 $\int_C f(x,y)dx$ を定めることもできる(はずで、適切な条件の下で上の定義と一致するはず)。このような定義にしておくと、曲線の微分可能性を弱めることができる(はず)。

簡単な例で計算してみよう。

!!! example "例1"
    単位円周(を左回りに一周する曲線)を $C$ とする。このとき、$C$ 上の点は $(\cos \theta, \sin \theta)$ ($0 \leq \theta \leq 2\pi$)と表される。したがって、
    
    $$\begin{align*}
    \int_C (-y\,dx + x dy) &= \int_{\theta = 0}^{2\pi} \left(-\sin \theta (\cos \theta)' + \cos \theta (\sin \theta)' \right) d\theta\\
    &= \int_{\theta=0}^{2\pi} (\sin^2 \theta + \cos^2 \theta)d \theta\\
    &= 2\pi
    \end{align*}$$

    である。

定義では曲線を $C^1$ 級としていたが、折れ線のような曲線を考えることも実用上重要である。