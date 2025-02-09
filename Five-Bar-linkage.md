<center>

# Five Bar dynamics 
## Define angles 


## Find the leg length and $\phi_0$

```math
\Large
\begin{cases} 
x_B + l_2\cos(\phi_2) = x_D + l_3 \cos(\phi_3) \\
y_B + l_2\sin(\phi_2) = x_D + l_3 \sin(\phi_3)
\end{cases} 
```


## Find the derivative of angle formula.

<img src="./Images/fivebar.png" width="500"/>

We now have all $ \Large\phi = \begin{bmatrix} \phi_0 \\ \phi_1 \\ \phi_2 \\ \phi_3 \\ \phi_4 \end{bmatrix}$

From the encoder, we can get $\dot{\phi_1}$ and $\dot{\phi_4}$

Find the derivative of the function we used for finding $\phi_2$

```math
\Large
\begin{cases} 
\dot x_B - l_2\dot \phi_2\sin(\phi_2) = \dot x_D - l_3\dot \phi_3 \sin(\phi_3) \\
\dot y_B + l_2\dot \phi_2\cos(\phi_2) = \dot y_D + l_3\dot \phi_3 \cos(\phi_3)
\end{cases} 
```

We can get:

$
\LARGE
\dot \phi_2 = \frac{(\dot x_D -\dot x_B )\cos(\phi_3) + (\dot y_D -\dot y_B )\sin(\phi_3)}{l_2\sin(\phi3 -\phi2)}
$


```math
\Large
\begin{cases} 
\dot x_B = -l_1\dot \phi_1\sin(\phi_1) \\
\dot y_B = l_1\dot \phi_1\cos(\phi_1) \\
\dot x_D = -l_4\dot \phi_4\sin(\phi_4) \\
\dot y_D = l_4\dot \phi_4\cos(\phi_4) \end{cases} 
```



Then find: 

```math
\Large
\begin{cases} 
\dot x_C = -l_1\dot \phi_1\sin(\phi_1) - l_2\dot \phi_2 \sin(\phi_2) \\
\dot y_C = l_1\dot \phi_1\cos(\phi_1) + l_2\dot \phi_2 \cos(\phi_2)
\end{cases} 
```






Since $\Large \phi_0 = \arctan(\frac{y_C}{x_C-l_5/2})$ we can get: 

```math
\Large
\begin{cases}
\dot \phi_0 = \frac{(x_C-l_5/2)\dot y_C + y_C\dot x_C}{(x_C-l_5/2)^2+y_C^2} \\
\dot L_0 = \sqrt{(\dot x_C^2 + \dot y_C^2)}
\end{cases} 
```



Note:  $l_2 = l_3$ and $l_1 = l_4$ in many design cases. 

