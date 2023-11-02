# 複素共役

複素数 $z = x+iy$ に対して、$\overline{z} := x - iy$ とおき、これを $z$ の **複素共役** という。

!!! theorem "補題"
    $z, w \in \mathbb{C}$ に対して、以下が成り立つ：

    (1) $\overline{z+w} = \overline{z} + \overline{w}$

    (2) $\overline{zw} = \overline{z} \cdot \overline{w}$

**証明** $z = a+bi$, $w=c+di$ とおく。

(1) $\overline{z+w} = \overline{a+bi + c+di} = (a+c) - (b+d)i = (a-bi) + (c-di) = \overline{z} + \overline{w}$ となる。

(2) $\overline{zw} = \overline{(a+bi)(c+di)} = \overline{(ac-bd) + (ad+bc)i} = (ac-bd)-(ad+bc)i = (a-bi)(c-di) = \overline{z}\cdot \overline{w}$となる。$\square$

補題を元に、以下を証明する：

!!! theorem "定理"
    $f$ を実数係数の多項式とする。このとき、任意の複素数 $z \in \mathbb{C}$ に対して、
    $$\overline{f(z)} = f(\overline{z}) $$
    が成り立つ。

**証明** まず、 $f(z) = z^n$ の場合に $n$ に関する帰納法で示す。($0, 1 \in \mathbb{R}$ だから、これは実数係数の多項式であることを一応注意しておく。)

$n=0$ ならば、$f(z) = 1$ だから、$\overline{f(z)} = \overline{1} = 1 = f(\overline{z})$ である。

$n-1$ で成り立つとすると、補題(2)より、$\overline{f(z)} = \overline{z \cdot z^{n-1}} = \overline{z} \cdot \overline{z^{n-1}}= \overline{z} \cdot \overline{z}^{n-1} = \overline{z}^n$ が成り立つ。これにより、$f(z) = z^n$ の場合に成立することが示された。

つぎに、$f(z) = a_n z^n$ が単項式である場合に示す。このときは、補題(2)と今示したことから、
$$\overline{f(z)} = \overline{a_n z^n} = \overline{a_n} \overline{z^n} = a_n \overline{z}^n = f(\overline{z}) $$
が成り立つ。

最後に、$f(z) = \sum_{i=0}^n a_i z^i$ が一般の多項式の場合に $n$ に関する帰納法で示す。

$n=0$ のときは、$f(z) = a_0$ は定数項しかもたない。このときは、$\overline{f(z)} = \overline{a_0} = a_0 = f(\overline{z})$ である。

$n-1$ で成り立つとすると、補題(1)と単項式の場合に示したことから、

$$ \begin{align*}\overline{f(z)} &= \overline{a_n z^n + (a_{n-1} z^{n-1} + \cdots + a_0)} \\
&= \overline{a_n z^n} + \overline{a_{n-1} z^{n-1} + \cdots + a_0} \\
&= a_n \overline{z}^n + a_{n-1}\overline{z}^{n-1} + \cdots + a_0 \\
&= f(\overline{z})\end{align*} $$

が成り立つ。これで全ての場合が証明された。$\square$