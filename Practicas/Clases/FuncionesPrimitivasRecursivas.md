# Funciones primitivas recursivas


### Funciones iniciales

- $n(x) = 0$
- $s(x) = x + 1$
- proyecciones: $u^n_i(x_1, ..., x_n) = x_i \text{ para } i \in \{1,...,n\}$

Hay infinitas funciones $u^n_i$. Por lo tanto, hay infinitas funciones iniciales.


### Composicion

**Definicion**

Sea $f: \N^k \to \N$ y $g_k: \N^n \to \N$




### Recursion primitiva

**Definicion**

$h: \N^{n+1} \to \N$ se obtiene a partir de $g:N^{n+2} \to \N$ y $f:N^n \to \N$ por **recursion primitiva** si:

$$ h(x_1, ..., x_n, 0) = f(x_1, ..., x_n)$$

$$ h(x_1, ..., x_n, t + 1) = g(h(x_1, ..., x_n, t), x_1 , ..., x_n, t)$$

- _Nota_: En este contexto vamos a considerar que una funcion 0-aria es una constante.


### Recursion primitiva

Los predicados p.r. son simplemente funciones que toman valores entre 0 y 1.

- 1 se interpreta como verdadero
- 0 se interpreta como falso


Si p y q son predicados p.r. entonces: $\n p, p \vee q, p \wedge q$ tambien son predicados p.r.


### Definicion por casos

Sean $h,g: \N^n \to \N$ funciones p.r. y sea $p: \N^n \to \{0,1\}$ un predicado p.r. La funcion:

$$f(x_1, ..., x_n) = $$



### Codificacion de pares

Definimos la funcion primitiva recursiva

$$\langle x,y \rangle = 2^x (2y + 1) - 1$$


**Proposicion**
Hay una unica solucion $(x,y)$ a la ecuacion $\langle x,y \rangle = z$


**Demostracion**

- $x$ es el maximo numero tal que $2^x | (z+1)$
- $y = ((z+1)/2^x - 1)/2$

### Observadores de pares

Los observadores del par $\langle x,y \rangle = z$ son: 
- $l(z) = x$
- $r(z) = y$

**Proposicion**
Los observadores de pares son primitivas recursivas

Ejemplo:

- $\langle 2, 5 \rangle = 2^2(2.5+1)-1 = 43$
- $l(43) = 2$
- $r(43) = 5$


$$fib'(0) = \langle fib(0), fib(1) \rangle$$

$$l(fib'(0)) = fib(0) = 0$$
$$r(fib'(0)) = fib(1) = 1$$

$$fib'(n+1) = \langle fib(n+1), fib(n+2) \rangle = \langle fib(n+1), fib(n+1) + fib(n) \rangle$$

$$= \langle r(fib'(n)), r(fib'(n)) + l(fib'(n)) \rangle$$


### Sumatorias y productorias

Si $f: \N^{n+1} \to \N$ son funciones p.r., entonces tambien lo son las siguientes funciones:

$$ g(y, x_1, ..., x_n) = \sum_{t=0}^y f(t, x_1, ..., x_n)$$
$$ h(y, x_1, ..., x_n) = \prod_{t=0}^y f(t, x_1, ..., x_n)$$


### Codificacion de secuencias

El **numero de Gödel** de la secuencia $a_1, ..., a_n$ es el numero :

$$[a_1, ..., a_n] = \prod_{i=1}^n p^{a_i}_i$$

donde $p_i$ es el i-esimo primo ($i\geq 1$)

Por ejemplo el numero de Gödel de la secuencia

$$1,3,3,2,2$$

es 

$$[1,3,3,2,2] = 2^1 3^3 5^3 7^2 11^2 = 40020750$$

### Propiedades de la codificacion de secuencias


**Teorema**

Si $[a_1, ..., a_n] = [b_1, ..., b_n]$ entonces $a_i = b_i$ para todo $i \in \{1,...,n\}$

**Demostracion**

Por la factorizacion unica en primos. (Teorema fundamental de la aritmetica)


**Observadores**
Los observadores de la secuencia $x = [a_1, ..., a_N]$ son:

- $x[i] = a_i$

- $|x| = \text{ longitud de } x$



### Lenguajes primitivos recursivos