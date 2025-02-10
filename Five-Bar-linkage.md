<div align="center">

# Five Bar Inverse Kinematics and Virtual Model Control
</div>

:green_circle:[1. Find leg length and $\theta_0$](#1-find-leg-length-and)\
:green_circle:[2. Find equations for velocity](#2-find-equations-for-velocity)\
:red_circle:[3. Virtual Model Control](#3-virtual-model-control)

<div align="center">

## 1. Find leg length and $\theta_0$
<img src="./Images/fivebar.png" width="500"/>

##

To find $\theta_2$
<div id="1.1"style="padding-top: 50vh; margin-top: -50vh;"></div>

```math
\Large\tag{1.1}
\begin{cases} 
x_B + L_2\cos(\theta_2) = x_D + L_3 \cos(\theta_3) \\
y_B + L_2\sin(\theta_2) = x_D + L_3 \sin(\theta_3)
\end{cases} 
```
<div id="1.2"style="padding-top: 50vh; margin-top: -50vh;"></div>

##

Move $x_D$ to the left side and Square both sides
```math
\Large\tag{1.2}
\begin{cases} 
(x_B + L_2\cos(\theta_2)-x_D)^2 = (L_3 \cos(\theta_3))^2 \\
(y_B + L_2\sin(\theta_2)-y_D)^2 = (L_3 \sin(\theta_3))^2
\end{cases} 
```
##
Solve [(1.2)](#1.2) we get
```math
\Large\tag{1.3}
A\cdot cos(\theta_2) + B\cdot sin(\theta_2) = C
```
```math
\Large
\begin{cases} 
A = 2 \cdot L_2 \cdot (x_B - x_D) \\
B = 2 \cdot L_2 \cdot (y_B - y_D) \\
C = L_3^2 - L_{BD}^2 - L_2^2 \\
L_{BD} = \sqrt{(x_B - x_D)^2 + (y_B - y_D)^2}
\end{cases} 
```
## 
```math
\Large \tag{1.4}
\begin{cases} 
\theta_2 = 2\cdot tan^{-1}(\frac{B\pm \sqrt{A^2+B^2-C^2}}{A+C})\\
\theta_3 = 2\cdot tan^{-1}(\frac{(-B)\pm \sqrt{A^2+B^2-C^2}}{(-A)+C})
\end{cases} 
```

##
We can find the (x,y) for point C and solve the $L_0$,
```math
\Large\tag{1.6}
\begin{cases} 
x_C = L_1\cos(\theta_1) + L_2 \cos(\theta_2) \\
y_C = L_1\sin(\theta_1) + L_2 \sin(\theta_2)
\end{cases} 
```
<div id="1.7"style="padding-top: 50vh; margin-top: -50vh;"></div>

##
```math
\Large\tag{1.7}
\begin{cases} 
L_0      = \sqrt{(x_C - \frac{L_5}{2})^2 + y_C^2} \\
\theta_0 = tan^{-1}(\frac{y_C}{x_C-\frac{L_5}{2}})
\end{cases} 
```
##


## 2. Find equations for velocity

We now have

```math 
\Large\theta = \begin{bmatrix} \theta_0 \\ \theta_1 \\ \theta_2 \\ \theta_3 \\ \theta_4 \end{bmatrix}
```
##
From the encoder, we can get $\dot{\theta_1}$ and $\dot{\theta_4}$. We have a great idea that we can use encoder data instead of the derivative of angle data to find the $\dot\theta_0$

Find the derivative of [(1.1)](#1.1) to find $\dot\theta_2$

```math
\Large\tag{2.1}
\begin{cases} 
\dot x_B - L_2\dot \theta_2\sin(\theta_2) = \dot x_D - L_3\dot \theta_3 \sin(\theta_3) \\
\dot y_B + L_2\dot \theta_2\cos(\theta_2) = \dot y_D + L_3\dot \theta_3 \cos(\theta_3)
\end{cases} 
```
##
We can get:

```math
\Large\tag{2.2}
\dot \theta_2 = \frac{(\dot x_D -\dot x_B )\cos(\theta_3) + (\dot y_D -\dot y_B )\sin(\theta_3)}{L_2\sin(\theta3 -\theta2)}
```

```math
\Large
\begin{cases} 
\dot x_B = -L_1\dot \theta_1\sin(\theta_1) \\
\dot y_B = L_1\dot \theta_1\cos(\theta_1) \\
\dot x_D = -L_4\dot \theta_4\sin(\theta_4) \\
\dot y_D = L_4\dot \theta_4\cos(\theta_4) \end{cases} 
```
##
Then find: 
```math
\Large\tag{2.3}
\begin{cases} 
\dot x_C = -L_1\dot \theta_1\sin(\theta_1) - L_2\dot \theta_2 \sin(\theta_2) \\
\dot y_C = L_1\dot \theta_1\cos(\theta_1) + L_2\dot \theta_2 \cos(\theta_2)
\end{cases} 
```
##
From [(1.7)](#1.7) we can get: 
```math
\Large\tag{2.4}
\begin{cases}
\dot \theta_0 = \frac{(x_C-\frac{L_5}{2})\dot y_C + y_C\dot x_C}{(x_C-\frac{L_5}{2})^2+y_C^2} \\
\dot L_0 = \sqrt{(\dot x_C^2 + \dot y_C^2)}
\end{cases} 
```

Note:  $L_2 = L_3$ and $L_1 = L_4$ in many design cases. 
##
## 3. Virtual Model Control




## Source

[1]. 五连杆运动学解算与VMC - 韭菜的菜的文章 - 知乎
https://zhuanlan.zhihu.com/p/613007726

[2]. 轮腿机器人-五连杆正运动学解算 - https://blog.csdn.net/weixin_44223883/article/details/137712455
