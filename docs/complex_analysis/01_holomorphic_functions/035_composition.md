# 合成関数の微分

複素微分についても合成関数の微分の公式が成り立つ。

!!! proposition "命題"
    $\Omega_1, \Omega_2 \subset \mathbb{C}$ を領域として、$f: \Omega_1 \to \Omega_2$, $g: \Omega_2 \to \mathbb{C}$ とする。$z \in \Omega_1$ に対して、$f$ は $z$ において複素微分可能、$g$ は $f(z)$ において複素微分可能であるとする。このとき、合成関数 $g \circ f$ は $z$ において複素微分可能であり、
    $$(g \circ f)' (z) = g'(f(z)) f'(z) $$
    が成り立つ。

ここで、合成関数 $g \circ f$ は、$(g \circ f)(z) := g(f(z))$ により定まる関数である。

合成関数の微分は、気持ちとしては、

- 関数 $f$ によって $z$ の周りが $f'(z)$ 倍される
- 関数 $g$ によって $f(z)$ の周りが $g'(f(z))$ 倍される
- したがって、$f$ と $g$ を続けて当てると $z$ の周りが $g'(f(z)) \cdot f'(z)$ 倍される

ということを言っている。

(以下の証明も基本的にこの説明と同じ筋ではあると思うんですけど、かなり大変なので、$\epsilon$-$\delta$ による極限の定義に慣れてない人は飛ばしても良いと思います。こんなに大変じゃなくてもいいと思うんですけど……)

証明の前に、次の補題を用意する：

!!! lemma "補題"
    $\Omega \subset \mathbb{C}$ を領域として、$f: \Omega \to \mathbb{C}$ を関数とする。$f$ が $z \in \Omega$ において複素微分可能であるとする。このとき、ある $C > 0$ と $\epsilon>0$ が存在して、$|\Delta z|< \epsilon$のとき、
    $$|f(z+\Delta z) - f(z)|  \leq C|\Delta z| $$
    が成り立つ。

**証明**
$f$ が $z$ において複素微分可能だから、
$$f(w) = f(z) + f'(z)(w-z) + r(w) $$
と書いたとき、
$$\lim_{w \to z} \frac{|r(w)|}{|w-z|} = 0 $$
である。特に、ある $\epsilon>0$ が存在して、$|w-z| < \epsilon$ のとき $\displaystyle\frac{|r(w)|}{|w-z|} < 1$ となる。すると、$|w-z| < \epsilon$ のとき、

$$\begin{align*}|f(w) - f(z)| &= |f'(z)(w-z) + r(w)|\\
&\leq |f'(z)(w-z)| + |r(w)| \\
&\leq |f'(z)||w-z| + |w-z|\\
&= (|f'(z)| + 1) |w-z|\end{align*}$$

である。$C := |f'(z)| + 1$ とおいて $w-z = \Delta z$ と書くと結論が得られる。$\square$

**命題の証明**
$f$ と $g$ の一次近似の式をそれぞれ書くと、
$$f(z + \Delta z) = f(z) + f'(z)\Delta z + r_f(z + \Delta z) $$
$$g(w + \Delta w) = g(w) + g'(w)\Delta w + r_g(w + \Delta w) $$
となる。$w = f(z)$, $\Delta w = f(z + \Delta z) - f(z)$ をそれぞれ代入して、

$$\begin{align*}
g(f(z + \Delta z)) &= g(f(z)) + g'(f(z)) (f(z+\Delta z) - f(z)) + r_g(w+\Delta w) \\
&= g(f(z)) + g'(f(z))(f'(z) \Delta z + r_f(z+\Delta z)) + r_g(w + \Delta w) \\
&= g(f(z)) + g'(f(z)) f'(z) \Delta z + g'(f(z)) r_f(z + \Delta z) + r_g (w + \Delta w) 
\end{align*}
$$

となる。$r_f$ の項が $o(\Delta z)$ であることはすでに分かっている。以下、$r_g$ の項をチェックする。

補題より、ある $C > 0 $ と $\epsilon>0$ が存在して、$|\Delta z| < \epsilon$ のとき
$$|f(z + \Delta z) - f(z)| \leq C |\Delta z| $$
が成り立つ。
$f(z + \Delta z) -f(z) = \Delta w$ と書くと、$|\Delta z| < \epsilon$ のとき
$$|\Delta w| \leq C |\Delta z| $$
となる。

$\epsilon'>0$ を任意にとって固定する。$r_g$ が $o(\Delta w)$ だったので、ある $\delta>0$ が存在して、 $|\Delta w| < \delta$ のとき $|r_g(w + \Delta w)| \leq \epsilon' |\Delta w|$ が成り立つ。すると、$|\Delta z| < \min(\epsilon, \frac{\delta}{C})$ のとき、$|\Delta w| \leq C |\Delta z| \leq \delta$ となるので、
$$|r_g(w + \Delta w)| \leq \epsilon' |\Delta w| \leq \epsilon' C |\Delta z| $$
である。$\epsilon'$ は任意なので、これで
$$\lim_{\Delta z \to 0}\frac{|r_g(w + \Delta w)|}{|\Delta z|}= 0 $$
であることがわかる。

以上により、$g\circ f$ の $z$ における一次近似の式が得られたので、$g \circ f$ は $z$ において複素微分可能である。また、その微分係数が $g'(f(z)) f'(z)$ であることがわかる。$\square$