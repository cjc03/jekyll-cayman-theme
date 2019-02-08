#  行列式(determinant)

## Why determinant?

高等代数中一个重要的问题即求解线性方程组，即形如：$\left\{ \begin{array}{l}	a_{11}x_1+a_{12}x_2+\cdots +a_{1n}x_n=b_1\\	a_{21}x_1+a_{22}x_2+\cdots +a_{2n}x_n=b_2\\	\cdots \,\,\cdots \,\,\cdots \,\,\cdots\\	a_{m1}x_1+a_{m2}x_2+\cdots +a_{mn}x_n=b_m\\\end{array} \right.$的方程组求解问题，行列式正式为了便捷、有效的解决这一问题的特殊情况：$m=n$而诞生的.

## 二阶行列式

先从简单情形分析，考虑$n=2$时，$\left\{ \begin{array}{l}	a_{11}x_1+a_{12}x_2=b_1\ \left( 1 \right)\\	a_{21}x_1+a_{22}x_2=b_2\ \left( 2 \right)\\\end{array} \right.$，假设该方程组有解，我们通过消元法得到：

$(1)\times a_{22}-(2)\times a_{12}:$ $(a_{11}a_{22}-a_{21}a_{12})x_1=a_{22}b_1-a_{12}b_2$，于是有 $x_1=\frac{a_{22}b_1-a_{12}b_2}{a_{11}a_{22}-a_{21}a_{12}}$

任一个有解的二阶线性方程组的解都可如此表示，为了简化表达，我们定义二阶行列式：$\left| \begin{matrix} a_{11}&a_{12}\\a_{21}&_{22}\\\end{matrix} \right|\xlongequal{\text{def}}a_{11}a_{22}-a_{21}a_{12}$，于是有：$$x_1=\frac{\left| \begin{matrix}	b_1&		a_{12}\\	b_2&		a_{22}\\\end{matrix} \right|}{\left| \begin{matrix}	a_{11}&		a_{12}\\	a_{21}&		a_{22}\\\end{matrix} \right|},同理x_2=\frac{\left| \begin{matrix}	a_{11}&		b_1\\	a_{21}&		b_2\\\end{matrix} \right|}{\left| \begin{matrix}	a_{11}&		a_{12}\\	a_{21}&		a_{22}\\\end{matrix} \right|}$$.

## 三阶行列式

考虑$n=3$时，$\left\{ \begin{array}{l}	a_{11}x_1+a_{12}x_2+a_{13}x_3=b_1\ \left( 4 \right)\\	a_{21}x_1+a_{22}x_2+a_{23}x_3=b_2\ \left( 5 \right)\\	a_{31}x_1+a_{32}x_2+a_{33}x_3=b_3\ \left( 6 \right)\\\end{array} \right.$，同样是假设其有解，利用消元法解这个方程组.

待定$u,v,w$，$(4)\times u+(5)\times v+(6)\times w:$考虑方程组$\left\{ \begin{array}{l}	\left( a_{11}u+a_{21}v+a_{31}w \right) x_1=ub_1+vb_2+wb_3\ \ \left( 7 \right)\\	a_{12}u+a_{22}v+a_{32}w=0\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \left( 8 \right)\\	a_{13}u+a_{23}v+a_{33}w=0\ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ \left( 9 \right)\\\end{array} \right.$,将$(8),(9)$改写为：$\left\{ \begin{array}{l}	a_{12}\frac{u}{w}+a_{22}\frac{v}{w}=-a_{32}\ \left( 10 \right)\\	a_{13}\frac{u}{w}+a_{23}\frac{v}{w}=-a_{33}\ \left( 11 \right)\\\end{array} \right.$，假设其有解，由$n=2$情形可知，
$$
\frac{u}{w}=\frac{\left| \begin{matrix}
	-a_{32}&		a_{22}\\
	-a_{33}&		a_{23}\\
\end{matrix} \right|}{\left| \begin{matrix}
	a_{11}&		a_{22}\\
	a_{13}&		a_{23}\\
\end{matrix} \right|}=\frac{\left| \begin{matrix}
	a_{22}&		a_{23}\\
	a_{32}&		a_{33}\\
\end{matrix} \right|}{\left| \begin{matrix}
	a_{11}&		a_{22}\\
	a_{13}&		a_{23}\\
\end{matrix} \right|}\text{，}\frac{v}{w}=\frac{\left| \begin{matrix}
	a_{12}&		-a_{32}\\
	a_{13}&		-a_{33}\\
\end{matrix} \right|}{\left| \begin{matrix}
	a_{11}&		a_{22}\\
	a_{13}&		a_{23}\\
\end{matrix} \right|}=-\frac{\left| \begin{matrix}
	a_{12}&		a_{13}\\
	a_{32}&		a_{33}\\
\end{matrix} \right|}{\left| \begin{matrix}
	a_{11}&		a_{22}\\
	a_{13}&		a_{23}\\
\end{matrix} \right|}.
$$


令$u=\left| \begin{matrix}	a_{22}&		a_{23}\\	a_{32}&		a_{33}\\\end{matrix} \right|\text{，}v=-\left| \begin{matrix}	a_{12}&		a_{13}\\	a_{32}&		a_{33}\\\end{matrix} \right|\text{，}w=\left| \begin{matrix}	a_{11}&		a_{22}\\	a_{13}&		a_{23}\\\end{matrix} \right|$，

由$(7)$知，$x_1=\frac{ub_1+vb_2+wb_3}{a_{11}u+a_{21}v+a_{31}w}$，为了简化表达，进而给出三阶行列式的递归定义，

$\left| \begin{matrix}	a_{11}&		a_{12}&		a_{13}\\	a_{21}&		a_{22}&		a_{23}\\	a_{31}&		a_{32}&		a_{33}\\\end{matrix} \right|\xlongequal{\text{def}}a_{11}\left| \begin{matrix}	a_{22}&		a_{23}\\	a_{32}&		a_{33}\\\end{matrix} \right|-a_{21}\left| \begin{matrix}	a_{12}&		a_{13}\\	a_{32}&		a_{33}\\\end{matrix} \right|+a_{31}\left| \begin{matrix}	a_{11}&		a_{22}\\	a_{13}&		a_{23}\\\end{matrix} \right|$，

那么$x_1$可表示为$x_1=\frac{\left| \begin{matrix}	b_1&		a_{12}&		a_{13}\\	b_2&		a_{22}&		a_{23}\\	b_3&		a_{32}&		a_{33}\\\end{matrix} \right|}{\left| \begin{matrix}	a_{11}&		a_{12}&		a_{13}\\	a_{21}&		a_{22}&		a_{23}\\	a_{31}&		a_{32}&		a_{33}\\\end{matrix} \right|}$，同理，$x_2,x_3$也可由相应表述，这样我们就能用三阶行列式简洁的将一切有解的线性方程组的解表示出来.

- 定义余子式后，上述三阶行列式也可看作将行列式按第一列展开
- 若将递归定义中的二阶行列式写成元素乘积的形式，则得到了三阶行列式的组合定义，也是我们熟知的行列式定义

## $n$阶行列式

有了二阶行列式、三阶行列式的定义，我们就可以通过数学归纳法给出$n$阶行列式的递归定义，$\det \boldsymbol{A}=\left| \begin{matrix}	a_{11}&		a_{12}&		\cdots&		a_{1n}\\	a_{21}&		a_{22}&		\cdots&		a_{2n}\\	\vdots&		\vdots&		\ddots&		\vdots\\	a_{n1}&		a_{n2}&		\cdots&		a_{nn}\\\end{matrix} \right|\left( \ast \right)$.

$n=1$时，$\left( \ast \right)$定义为$det \boldsymbol{A}=a_{11}$.

假定对$n-1$阶行列式已定义了它们的值，则$\forall i,j\left( 1\le i,j\le n \right) ,M_{ij}$有定义，则$det \boldsymbol{A}\xlongequal{\text{def}}a_{11}A_{11}+a_{21}A_{21}+...a_{n1}A_{n1}$，$A_{ij}=(-1)^{i+j}M_{ij}$.

我们将从行列式递归定义的角度依次推出行列式的性质.








