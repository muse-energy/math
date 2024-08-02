# Levi-Civita接続

Riemann多様体上では、**Levi-Civita接続**という"良い"接続が一意的に存在することが知られていて、これを標準的な接続として用いるようである。Levi-Civita接続は、以下のふたつの条件をみたす接続をいう：

- 計量を保つ。
- ねじれがない。

それぞれについて順に説明する。

## 計量を保つ接続
!!! definition "定義"
    $(M, g)$ をRiemann多様体とする。$M$ 上の接続 $\nabla$ が **計量を保つ** とは、任意の $X, Y, Z \in \mathfrak{X}(M)$ に対して、
    $$ \nabla_X \langle Y, Z \rangle_g = \langle \nabla_X Y, Z \rangle_g + \langle Y, \nabla_X Z \rangle_g $$
    が成り立つことをいう。
この定義は、「計量 $g$ に関しても $\nabla$ がLeibniz則をみたすかのようにふるまう」と言っている。計量を保つ接続について、次の特徴付けが知られている：

!!! proposition "命題 ([Lee][^Lee]のProposition 5.5の一部)"
    $(M, g)$ をRiemann多様体とし、$\nabla$ を $M$ 上の接続とする。このとき、以下は同値である。
    
    - (a) $\nabla$ は計量 $g$ を保つ。
    - (b) $g$ は $\nabla$ に関して平行である： $\nabla g \equiv 0$
    - (c) smooth local frame $(E_i)$ について、
    $$ \Gamma^\ell_{ki} g_{\ell j} + \Gamma^{\ell}_{kj} g_{i \ell} = E_k (g_{ij}) $$

計量(というかテンソル？)に対しても接続が自然に拡張される話をしていない気がする。

[^Lee]: John M. Lee: Introduction to Riemannian Manifolds, Second Edition. Springer, Graduate Texts in Mathematics, 2018.