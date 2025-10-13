# Hilbert空間の復習

以下、$\mathcal{H}$ を**Hilbert空間**とする。すなわち、$\mathbb{R}$-双線形 (or $\mathbb{C}$-半双線形(後述))かつ正定値な内積 $\langle \cdot, \cdot\rangle: \mathcal{H} \times \mathcal{H} \to \mathbb{R} (\text{or }\mathbb{C})$ を備えた $\mathbb{R}$- (or $\mathbb{C}$-) 線形空間であって、内積から定まるnorm $\|x\|^2 := \langle x, x \rangle$ に関して完備であるようなものとする。

**半双線形**とは、ここではひとつめの引数に関しては$\mathbb{C}$-線形で、ふたつめの引数に関しては$\mathbb{C}$-反線形(スカラー倍が共役で作用)ということ。

以下では係数体 $\mathbb{K}$ を明記しないが、$\mathbb{K} = \mathbb{R}$ であるか $\mathbb{K} = \mathbb{C}$ であるかのどちらかだとする。

## Hilbert空間の性質

Hilbert空間の性質を軽くみていこう。

!!! proposition "Cauchy-Schwarzの不等式"
    $\mathcal{H}$ をHilbert空間とする。このとき、$x, y \in \mathcal{H}$ に対して、
    $$ |\langle x, y \rangle| \leq \|x\|\|y\| $$
    が成り立つ。


!!! proposition "和と内積の連続性"
    $\mathcal{H}$ をHilbert空間とする。$\lambda \in \mathbb{K}$ を係数体の元とする。このとき、
    $$ (x,y) \mapsto x+y,\,\,\, x \mapsto \lambda x,\,\,\, (x, y) \mapsto \langle x, y\rangle $$
    は連続である。 

Hilbert空間 $\mathcal{H}$ とその部分空間 $S$ に対して、$S$ の**直交** $S^\perp$ を、
$$ S^{\perp} := \{x \in \mathcal{H} : \forall y \in S, \langle x, y \rangle = 0 \} $$
によって定める。

!!! theorem "直交分解"
    $\mathcal{H}$ をHilbert空間、$S \subset \mathcal{H}$ を閉部分空間とする。このとき、$\mathcal{H} \cong S \oplus S^{\perp}$ が成り立つ。この同型は次の意味で等長である：$x \in \mathcal{H}$ を $x = y_1+y_2$, $y_1 \in S, y_2 \in S^{\perp}$ と分解したとき(この分解は一意)、$\|x\|^2_\mathcal{H} = \|y_1\|^2_S + \|y_2\|^2_{S^\perp}$ が成り立つ。

!!! theorem "Rieszの表現定理"
    $\mathcal{H}$ を $\mathbb{R}$($\mathbb{C}$)-Hilbert空間とする。$\mathbb{R}$-線形写像 $L: \mathcal{H} \to \mathbb{R}$ ($\mathbb{C}$-反線形写像 $L: \mathcal{H} \to \mathbb{C}$)が
    $$ |Ly| \leq C \|y\|_\mathcal{H} \,\, (y \in \mathcal{H}) $$
    を満たすとする。ただし、$C\geq 0$ は $y$ によらない定数である。このとき、ある $x \in \mathcal{H}$ が存在して、
    $$ Ly = \langle x, y\rangle \,\, (y \in \mathcal{H}) $$
    かつ $\|x\|_\mathcal{H} \leq C$ が成り立つ。