### Вариант 9
$$
A =
\begin{pmatrix}
-6 & -1 & 0 & \cdots & 0 & 0 \\
-9 & -6 & -1 & \cdots & 0 & 0 \\
0 & -9 & -6 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & -6 & -1 \\
0 & 0 & 0 & \cdots & -9 & -6
\end{pmatrix}
$$

Порядок матрицы $n = 5$.

## Вывод реккурентого соотношения
Перепишем матрицу для удобства

$A =
\begin{pmatrix}
-6 & -1 & 0 & 0 & 0 \\
-9 & -6 & -1 & 0 & 0 \\
0 & -9 & -6 & -1 & 0 \\
0 & 0 & -9 & -6 & -1 \\
0 & 0 & 0 & -9 & -6
\end{pmatrix}$

Найдем определитель через разложение по 1 строке

$\triangle_n = (-6) \cdot (-1)^{1+1} \cdot M_{11}  + (-1) \cdot (-1)^{1+2} \cdot M_{12}$

$\triangle_n = (-6) \cdot M_{11}  - (-1) \cdot M_{12}$

$M_{11} = \begin{vmatrix}
-6 & -1 & 0 & 0\\
-9 & -6 & -1 & 0\\
0 & -9 & -6 & -1\\
0 & 0 & -9 & -6 \\
\end{vmatrix}
$

$M_{11}$ - это определитель матрицы $A_{n-1}$, которая имеет тот же вид что и матрица $A_{n}$, значит $M_{11} = \triangle_{n-1}$

$|A_n| = (-6) \cdot \triangle_{n-1}  - (-1) \cdot M_{12}$

$M_{12} = \begin{vmatrix}
-9 & -1 & 0 & 0 \\
0 & -6 & -1 & 0 \\
0 & -9 & -6 & -1 \\
0 & 0 & -9 & -6
\end{vmatrix}$

Найдем определитель через разложение по 1 столбцу

$M_{12} = (-9) \cdot \begin{vmatrix}
 -6 & -1 & 0 \\
 -9 & -6 & -1 \\
 0 & -9 & -6
\end{vmatrix} =  (-9) \cdot \triangle_{n-2}$

Подставляем, получаем линеййное однородное  реккурентное соотношение, с постоянными коэфициентами и глубиной 2

$\triangle_{n} = (-6) \cdot \triangle_{n-1}  - (-1) \cdot (-9) \cdot \triangle_{n-2}$

$\triangle_{n} = -6 \cdot \triangle_{n-1}  - 9 \cdot \triangle_{n-2}$

## Характеристическое уравнение

Проводим замену
$\triangle_{n} = \lambda^n$

$\lambda^n = -6 \lambda^{n-1} - 9 \lambda^{n-2}  | \frac{1}{\lambda^{n-2}}$

$\lambda^2 = -6 \lambda - 9$

$\lambda^2 + 6 \lambda + 9 = 0$

$(\lambda+ 3)^2 = 0$

$\lambda_1 = \lambda_2 = -3$