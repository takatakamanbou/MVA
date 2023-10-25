# 特異値分解と主成分分析

主成分分析では，データの分散共分散行列の固有値・固有ベクトルを計算に使いますが，実は，「特異値分解」を利用すると，分散共分散行列を計算しなくても，その固有値・固有ベクトルを求めることができます．
その理屈を理解して実際に計算してみましょう．

## Step1

任意の $m \times n$ 行列 $X$ は

$$
X = USV^{\top}
$$

と分解できます．ただし，&mathjax{\textrm{rank}(X) = r \leq \textrm{min}(m, n)}; として，

- &mathjax{U}; は &mathjax{m\times r}; 列直交行列（各列のベクトルが直交し大きさが1）
- &mathjax{V}; は &mathjax{n\times r}; 列直交行列
- &mathjax{S}; は &mathjax{r\times r}; 対角行列で，その対角要素 &mathjax{\sigma_1, \sigma_2, \ldots, \sigma_r}; は全て正

です．&mathjax{\sigma_1, \sigma_2, \ldots, \sigma_r}; を &mathjax{X}; の特異値といい，この行列分解を特異値分解といいます．

このとき，&mathjax{X^{\rm T}X}; を &mathjax{V}; と &mathjax{S}; を用いて表しなさい．

Step1 ができたらいったん takataka に見せてください．Step2 につながるお話をします．

*** Step2 [#s88f8bd1]

Step1 が（高橋の説明も含めて）分かると，データを表す &mathjax{N\times D}; 行列 &mathjax{X}; が与えられたとき（平均は &mathjax{\mathbf{0}}; とします），
&mathjax{X}; の分散共分散行列 &mathjax{\frac{1}{N}X^{\rm T}X}; を計算してからその固有値固有ベクトルを求める必要はなく，&mathjax{X}; を特異値分解した結果からそれらが求まることが分かります．
ex05notebookB の適当な箇所にセルを追加して，Vの固有値固有ベクトルをXの特異値分解（np.linalg.svd 使いましょう）を用いて計算して表示するコードを書きなさい．
