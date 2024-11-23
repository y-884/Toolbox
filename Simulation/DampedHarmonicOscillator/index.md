# 減衰振動
$$
    m \frac{d^2x}{dt^2} + c \frac{dx}{dt} + kx = 0
$$


## 厳密解
ここでは1階の連立微分方程式へと変換して解く方法を採用する.
$x_1 = x, x_2 = \frac{dx_1}{dt}$ とおくと, 減衰振動の微分方程式は次式に変換できる.
$$
    \frac{d}{dt}
    \left( \begin{array}{c}
        x_1 \\
        x_2
    \end{array}\right)
    =
    \left( \begin{array}{cc}
        0 & 1 \\
        -\omega^2 & -2\gamma
    \end{array}\right)
    \left( \begin{array}{c}
        x_1 \\
        x_2
    \end{array}\right)
    =
    A \mathbf{x}
$$
ここで $ \gamma = c/2m, \omega = \sqrt{k/m}$ とおいた.
行列 $A$ の固有値は固有方程式 $ | A - \lambda I | = 0 $を解いて 
$ \lambda = - \gamma \pm \sqrt{\gamma^2 - \omega^2} $ と得られる.


$ \gamma^2 - \omega^2 \neq 0 $ の場合, 2つの固有値を得る.
それぞれ $ \lambda_1, \lambda_2 $ とし, 対応する固有ベクトルを $ \mathbf{p}_1, \mathbf{p}_2 $ とする.
このとき, 行列 $A$ は次のように対角化できる.
$$
    P^{-1}AP = 
    \left(\begin{array}{cc}
        \lambda_1 & 0 \\
        0 & \lambda_2
    \end{array}\right) \\
    P = (\mathbf{p}_1 \ \mathbf{p}_2) \\
$$
$ \mathbf{x} = P \mathbf{y}$ となる $ \mathbf{y} = (y_1 \ y_2)^\top $ を導入すると, 減衰振動の微分方程式は更に次式で表される2つの独立した1階微分方程式へと変換できる.
$$
    \frac{d}{dt}
    \left( \begin{array}{c}
        y_1 \\
        y_2
    \end{array}\right)
    =
    \left( \begin{array}{cc}
        \lambda_1 & 0 \\
        0 & \lambda_2
    \end{array}\right)
    \left( \begin{array}{c}
        y_1 \\
        y_2
    \end{array}\right)
$$
これは簡単に解くことができ, 積分定数 $C_1, C_2$ を導入して $ y_1 = C_1 e^{\lambda_1 t}, y_2 = C_2 e^{\lambda_2 t}$ を得る.
$ \mathbf{x} = P \mathbf{y}$ によって $ \mathbf{x} $ に変換したあとに積分定数を改めて $C_1, C_2 $ と置き直すことで次式の解を得る.
$$
    x_1 = x = C_1 e^{\lambda_1 t} + C_2 e^{\lambda_2 t}
$$


$ \gamma^2 - \omega^2 = 0 $ の場合, 1つの固有値 $ \lambda_1 = -\gamma $を得る.
ところで, $ (A - \lambda_1 I )\mathbf{x} = \mathbf{0} $ を計算するとわかるが, 固有ベクトルは1つしか得られない.
つまり行列 $A$ は対角化できず, $ \gamma^2 - \omega^2 \neq 0 $ の場合の解き方を直接適用できない.
そこで, 対角化ではなくジョルダン標準形への変換を試みる.
固有値 $ \lambda_1$ に対応する固有ベクトルを $ \mathbf{p}_1 $ とし, $ (A - \lambda_1 I) \mathbf{p}_2 = \mathbf{p}_1 $ から得られる広義固有ベクトル $ \mathbf{p}_2 $ とする.
このとき, 行列 $A$ は次のようにジョルダン標準形へと変換できる.
$$
    S^{^-1} A S =
    \left(\begin{array}{cc}
        \lambda_1 & 1 \\
        0 & \lambda_1
    \end{array}\right) \\
    S = (\mathbf{p}_1 \ \mathbf{p}_2)
$$
$ \mathbf{x} = S \mathbf{y}$ となる $ \mathbf{y} = (y_1 \ y_2)^\top $ を導入すると, 減衰振動の微分方程式は更に次式へと変換できる.
$$
    \frac{d}{dt}
    \left( \begin{array}{c}
        y_1 \\
        y_2
    \end{array}\right)
    =
    \left( \begin{array}{cc}
        \lambda_1 & 1 \\
        0 & \lambda_1
    \end{array}\right)
    \left( \begin{array}{c}
        y_1 \\
        y_2
    \end{array}\right)
$$
これは $y_2　$ については簡単に解くことができ, 積分定数 $C_1 $ を導入して $ y_2 = C_1 e^{\lambda_1 t} $ を得る.
$ y_1　$ については合成関数の微分を考えることで, 積分定数 $C_2$ を導入して $ y_1 = ( C_1 t　＋ C_2) e^{\lambda_1 t} $ を得る.
$ \mathbf{x} = P \mathbf{y}$ によって $ \mathbf{x} $ に変換したあとに積分定数を改めて $C_1, C_2 $ と置き直すことで次式の解を得る.
$$
    x_1 = x = ( C_1 t + C_2) e^{\lambda_1 t}
$$


