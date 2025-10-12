# 自然変換

「関手の間の射」が自然変換である。

!!! definition "定義"
    $\mathsf{C}$, $\mathsf{D}$ を圏とし、$F, G: \mathsf{C} \to \mathsf{D}$ を関手とする。このとき、**自然変換** $\alpha: F \Rightarrow G$ は、以下のデータからなる：
    
    - それぞれの対象 $x \in \mathsf{C}$ に対して、$\mathsf{D}$ における射 $\alpha_x : Fx \to Gx$ が定まっている。
    - 任意の射 $f \in \mathsf{C}(x, y)$ に対して、以下の図式は可換である：
      $$ \begin{CD} Fx @>{Ff}>> Fy \\\\ @V{\alpha_x}VV @VV{\alpha_y}V \\\\ Gx @>{Gf}>> Gy \end{CD} $$