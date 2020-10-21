# $e$について
> 参考動画: 
> - https://www.youtube.com/watch?v=J-E4z-_Daps
> - https://www.youtube.com/watch?v=JBIZRL8T5a4
- $\displaystyle \lim_{x \to 0}(1+x)^\frac{1}{x}$は、$2.718...$に近づく
- $e = 2.718...$
- この時、$(1 + x)$は0に近づく
- $\frac{1}{x}$の$x$は0に近づくので、$\frac{1}{x}$は$\infty$に限りなく近づく
- $x$と$\frac{1}{x}$は逆数関係
- 練習問題
    - $\displaystyle \lim_{x \to 0}(1+\frac{x}{2})^\frac{1}{x}$
        - 1たす0に近づく、カッコの無限大乗 => $e$に関連する?
        - $\displaystyle \lim_{x \to 0}(1+\frac{x}{2})^\frac{1}{x} =\lim_{x \to 0}\{(1+\frac{x}{2})^\frac{2}{x}\}^\frac{1}{2}$ 
            - 逆数関係を作る($x$と$\frac{1}{x}$の関係)
            - $\frac{1}{2}$乗により補正計算
        - $\lim_{x \to 0}\{(1+\frac{x}{2})^\frac{2}{x}\}^\frac{1}{2} = \{e\} ^\frac{1}{2} = \sqrt e$ 

    - $\displaystyle \lim_{x \to 0}(1+3x)^\frac{1}{x}$
        - $\displaystyle \lim_{x \to 0}\{(1+3x)^\frac{1}{3x}\}^3 = e^3$ 
## 公式
### $e$の定義式
- $\displaystyle \lim_{x \to \infty}(1+\frac{1}{x})^x = e$
- $\displaystyle \lim_{x \to -\infty}(1+\frac{1}{x})^x = e$
### その他
- $\log{e} = ln$
- $e^x = exp(x)$