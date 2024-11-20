# Limites de la Computabilidad

- no todos los lenguajes son computables
- En esta practica veremos tecnicas para demostrar cuando un lenguaje es no computable.


## Diagonalizacion

- Tecnica para demostrar que un lenguaje no es copmputable por absurdo
- **Idea**: asumi que es computable y generar una funcion computbale que falle sobre una entrada particular.


### Ejemplo: HALT no es computable


Sea $HALT = \{ \langle \#(M), w \rangle | M(w) \downarrow \}$

Demostremolo por absurdo usando diagonalizacion

Asumamos que $HALT$ es computable, despues consideramos el programa P:

$\textbf{while } HALT(X,X) \neq 0 \textbf{ do \{ pass \} }$


La funcion computada por $P$ es total, ya que $HALT$ es computable:

$$\Psi_P^{(n)} = \begin{cases}
    \uparrow & \text{si } HALT(x,x) = 1 \\
    0 & \text{si } HALT(x,x) \neq 1  \
\end{cases}$$

Supongamos que $\#(P) = k$

Que sucede con $\langle k,k\rangle$? podemos decir que $\langle k,k\rangle \in HALT$ ?

Si $\langle k,k\rangle \in HALT$ $\Leftrightarrow$ $\Phi_k^{(1)} \downarrow$ (Por definicion de $HALT$)

$\Leftrightarrow$ $HALT(k,k) = 1$ (Por definicion de funcion caracteristica de $HALT$)

$\Leftrightarrow$ $\Phi_k^{(1)} \uparrow$ (Por definicion de $P$)

$\Leftrightarrow$ $HALT(k,k) = 0$ (Por definicion de funcion caracteristica de $HALT$)


### Otro ejemplo:


## Reducciones

Tecnica para demostrar que un lenguaje no es computable, utilizando otro lenguaje que sepamos que no es computable.

**Reducciones:** Sea $A,B \subseteq \Sigma^*$. Decimos que $A$ se reduce a $B$ si y solo si existe una funcion $f:\Sigma^* \to \Sigma^*$ total computable tal que $\forall w \in \Sigma^*, w \in A \Leftrightarrow f(w) \in B$

**Notacion:** $A \leq B$

## Lenguaje computables, computablemente enumerables y 

Consideremos un alfabeto $\Sigma$ y un lenguaje $L \subseteq \Sigma^*$.
Decimos que $L$ es un **lenguaje computable** si, considerando una codificacion de cadenas $\Sigma^* \to \mathbb{N}$, su predicado caracteristico 

$$p_L(x) = \begin{cases}
    1 & \text{si la cadena codificada por } x \in L\\
    0 & \text{si no} \
\end{cases}$$

es computable.

Si su predicado caracteristico es parcialmente computable, decimos que $L$ es un **lenguaje comptablemente enumerable (c.e)**

Si el predicado caracteristico del complemento del lenguaje $L$, notado $L^C$, es parcialmente computable, entocnes decimos que $L$ es **co-c.e.**


## Reducciones y computablidad

Si $A \leq B$, entonces:

- $B$ es computable, entonces $A$ es computable
- $B$ no es computablemente enumerable, entonces $A$ es computablemente enumerable

**Corolario**: Si $A \leq B$, entonces:

- $A$ no es computable, entonces $B$ no es computable
- $A$ no es computablemente enumerable, entonces $B$ no es computablemente enumerable

#### Pasos para usar reducibilidad

Para mostrar que $B$ no es computable usando reduccion:

1) Elegir un $A$ no computable conveniente
2) Mostrar que existe una funcion $f$ que efectivamente reduce $A$ en $B$
3) Mostrar que dicha funcion es computable
4) Explicitar que lema o corolario se usa para llegar al absurdo





## Propiedades

- $A$ es computable si y solo si $A \leq \{\lambda\}$

    - $\Rightarrow$) Tomar la funcion partida 
     $$f(w) = \begin{cases}
        \lambda & w \notin A \\
        a & \text{ si no } \\
     \end{cases}$$
    
    - $\Leftarrow$) Para ver si $w \in A$, veo si $f(w) = \lambda$

- Sea $Z$ computable, no trivial (osea que $Z \neq \empty$ y $Z \neq \Sigma^*$), entonces para todo $A$, $A$ es computable si y solo si $A \leq Z$

- La computablidad es cerrada por complemento. Es decir, si un lenguaje es computable, tambien lo es su complemento

    $$A \text{ es computable } \Leftrightarrow A^C \text{ es computable }$$

    Sin embargo, la condicion de ser computablemente enumerable no es cerrada por complemento

    Por ejemplo, $HALT$ es computablemente enumerable, pero $HALT^C$ no lo es

- $A$ es computable $\Leftrightarrow$ $A$ es computablemente enumerable y $A^C$ tambien es computablemente enumerable

    - $\Rightarrow$) Podemos usar la funcion caracteristica y su negacion.
    
    - $\Leftarrow$) Construyendo un programa que ejecute los programas de las funciones caracteristicas intercalando instrucciones de $A$ y $A^C$