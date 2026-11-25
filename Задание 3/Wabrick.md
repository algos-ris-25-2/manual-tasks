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

$$A =
\begin{pmatrix}
-6 & -1 & 0 & 0 & 0 \\
-9 & -6 & -1 & 0 & 0 \\
0 & -9 & -6 & -1 & 0 \\
0 & 0 & -9 & -6 & -1 \\
0 & 0 & 0 & -9 & -6
\end{pmatrix}$$

Найдем определитель через разложение по 1 строке

$$\triangle_n = (-6) \cdot (-1)^{1+1} \cdot M_{11}  + (-1) \cdot (-1)^{1+2} \cdot M_{12}$$

$$\triangle_n = (-6) \cdot M_{11}  - (-1) \cdot M_{12}$$

$$M_{11} = \begin{vmatrix}
-6 & -1 & 0 & 0\\
-9 & -6 & -1 & 0\\
0 & -9 & -6 & -1\\
0 & 0 & -9 & -6 \\
\end{vmatrix}
$$

$$M_{11} \text{ - это определитель матрицы } A_{n-1} \text{, которая имеет тот же вид что и матрица } A_{n}\text{, значит }M_{11} = \triangle_{n-1}$$

$$\triangle_n = (-6) \cdot \triangle_{n-1}  - (-1) \cdot M_{12}$$

$$M_{12} = \begin{vmatrix}
-9 & -1 & 0 & 0 \\
0 & -6 & -1 & 0 \\
0 & -9 & -6 & -1 \\
0 & 0 & -9 & -6
\end{vmatrix}$$

Найдем определитель через разложение по 1 столбцу

$$M_{12} = (-9) \cdot \begin{vmatrix}
 -6 & -1 & 0 \\
 -9 & -6 & -1 \\
 0 & -9 & -6
\end{vmatrix} =  (-9) \cdot \triangle_{n-2}$$

Подставляем, получаем линейное однородное  реккурентное соотношение, с постоянными коэфициентами и глубиной 2

$$\triangle_{n} = (-6) \cdot \triangle_{n-1}  - (-1) \cdot (-9) \cdot \triangle_{n-2}$$

$$\triangle_{n} = -6 \cdot \triangle_{n-1}  - 9 \cdot \triangle_{n-2}$$

Найдем базу рекурсии

$$\triangle_1= \begin{vmatrix}
-6
\end{vmatrix} = -6$$

$$\triangle_2= \begin{vmatrix}
-6 & -1 \\
-9 & -6
\end{vmatrix} = (-6) \cdot (-6) - ( (-9) \cdot (-1)) = 27$$


## Характеристическое уравнение

Проводим замену
$$\triangle_{n} = \lambda^n$$

$$\lambda^n = -6 \lambda^{n-1} - 9 \lambda^{n-2}  | \frac{1}{\lambda^{n-2}}$$

$$\lambda^2 = -6 \lambda - 9$$

$$\lambda^2 + 6 \lambda + 9 = 0$$

$$(\lambda+ 3)^2 = 0$$

$$\lambda_1 = \lambda_2 = -3$$

## Формула общего решения

Формула общего решения для кратных корней
$$\triangle_n = n \cdot A_1 \cdot \lambda_1^n + A_2 \cdot \lambda_1^n$$

$$\text {Подставляем } \lambda_1 = -3$$

$$\triangle_n = n \cdot A_1 \cdot -3^n + A_2 \cdot -3^n$$

$$\text {Подставим базу рекурсии }\triangle_1 = -6 \text { и } \triangle_2 = 27$$

$$\begin{cases}
-6 = 1 \cdot A_1 \cdot -3^1 + A_2 \cdot -3^1 \\
27 = 2 \cdot A_1 \cdot -3^2 + A_2 \cdot -3^2 
\end{cases}$$

$$\begin{cases}
-6 = -3 \cdot A_1 -3 \cdot A_2 \\
27 = 18 \cdot A_1 + 9 \cdot A_2 
\end{cases}$$

$$\begin{cases}
2 = A_1 + A_2 \\
3 = 2 \cdot A_1 + 1 \cdot A_2 
\end{cases}$$

Решаем уравнение методом подстановки, получаем корни

$$A_1 =A_2 = 1$$

Подставляем в формулу

$$\triangle_n = -3^n \cdot n -3^n$$

$$\triangle_n = -3^n \cdot (n + 1)$$

##  Значение определителя матрицы n=5

$$\triangle_5 = -3^5 \cdot (5 + 1)$$

$$\triangle_5 = -243 \cdot 6$$

$$\triangle_5 = -1458$$

## Проверка полученной формулы

Вычиление определителя 3 порядка вручную

$$\triangle_3 = \begin{vmatrix}
 -6 & -1 & 0 \\
 -9 & -6 & -1 \\
 0 & -9 & -6
\end{vmatrix} =  (-6)^3 + (-1)^2 \cdot 0 + (-9)^2 \cdot 0 - ((-6) \cdot 0 + (-9) \cdot (-1) \cdot (-6) + (-9) \cdot (-1) \cdot (-6))= -216 - (-108) = -108$$

Вычисление определителя 3 порядка по выведенной формуле

$$\triangle_3 = -3^3 \cdot (3 + 1)$$

$$\triangle_3 = -27 \cdot 4$$

$$\triangle_3 = -108$$
