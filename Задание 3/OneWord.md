# Команда OneWord
### Вариант 6

$$
A =
\begin{pmatrix}
-1 & 1 & 0 & \cdots & 0 & 0 \\
-2 & -1 & 1 & \cdots & 0 & 0 \\
0 & -2 & -1 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & -1 & 1 \\
0 & 0 & 0 & \cdots & -2 & -1
\end{pmatrix}
$$

Порядок матрицы $n = 7$.

### Решение

$a=-1; b=1; c=-2$

#### Составим рекуррентное соотношение:

Воспользуемся формулой нахождения определителя n-го порядка для 3-х диагональной матрицы:  
$$ \boxed{\Delta_n = a \cdot \Delta_{n-1} - bc \cdot \Delta_{n-2}}  $$

$ \Delta_n = -1 \cdot \Delta_{n-1} + 2 \cdot \Delta_{n-2}  $

#### Решим характеристическое уравнение:
Для линейного рекуррентного соотношения получаем уравнение:

$\lambda^n = -\lambda^{n-1} + 2 \lambda^{n-2}$

Делим обе части на $\lambda^{n-2} \neq 0$ (По теореме Виета свободный член является произведением двух корней, а так как коэфициент $bc$ не равен нулю, то и каждый из корней не равен нулю и деление возможно).

$\lambda^2+\lambda-2=0$

По теореме Виета $\lambda_1=1$ или $\lambda_2=-2$  

#### Общее решение рекуррентного уравнения (для разных корней):

$$\boxed{\Delta_n= A_1 \cdot \lambda_1^n + A_2 \cdot \lambda_2^n}$$

$$\Delta_n= A_1 \cdot 1^n + A_2 \cdot (-2)^n$$

Вычислим определители первого и второго порядка:

$$
\Delta_1=
\begin{vmatrix}
-1
\end{vmatrix}
=-1
$$


$$
\Delta_2=
\begin{vmatrix}
-1 & 1 \\
-2 & -1
\end{vmatrix}
=3
$$

Решим систему уравнений:
$$
\left\{\begin{aligned}
  -1=A_1-2A_2
  \\
  3=A_1+4A_2
\end{aligned}\right.
\;=>\;
\left\{\begin{aligned}
  A_1=\frac{1}{3} \\
  A_2=\frac{2}{3}
\end{aligned}\right.
$$

$$\Delta_n=\Delta_7=\frac{1}{3}\cdot1^7+\frac{2}{3}\cdot(-2)^7=\frac{1}{3}-\frac{256}{3}=-85$$


#### Проверяем:

$$\Delta_2=\frac{1}{3}\cdot1^2+\frac{2}{3}\cdot(-2)^2=\frac{1}{3}+\frac{8}{3}=\frac{9}{3}=3$$

$$
\Delta_3=
\begin{vmatrix}
-1 & 1 & 0 \\
-2 & -1 & 1 \\
0 & -2 & -1
\end{vmatrix}
=-5
$$

$$\Delta_3=\frac{1}{3}\cdot1^3+\frac{2}{3}\cdot(-2)^3=\frac{1}{3}-\frac{2}{3}\cdot8=\frac{1}{3}-\frac{16}{3}=-5$$