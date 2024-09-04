# Teorica 2 - Automatas finitos y Gramaticas Regulares


### Definicion (automata finito deterministico (AFD))

Es una 5-upla $<Q,\Sigma, \delta, q_0, F>$ donde

- $Q$ es un conjunto finito de estados

- $\Sigma$ el alfabeto de entrada

- $\delta: Q \times \Sigma \rightarrow Q$ es la funcion de transicion 

- $q_0 \in Q$ es el estado inicial

- $F \subseteq Q$ es el conjunto de estados finales


### Definicion (funcion de transicion generalizada $\delta$)

definimos $\delta: Q \times \Sigma^* \rightarrow Q$

- $\hat{\delta}(q,\lambda)=q$

- $\hat{\delta}(q,xa)= \delta(\delta(q,x),a)$, con $x\in \Sigma^*$ y $a \in \Sigma$

notar que $\delta(q,a) = \delta(\delta(q,\lambda), a) = \delta(q,a)$
Muchas veces usaremos simbolo $\delta$ para ambas funciones.

### Definicion (lenguaje aceptado por un AFD)

El lenguaje aceptado por un AFD $M=<Q,\Sigma, \delta, q_0, F>$, al que denotaremos $\mathcal{L}(M)$, es el conjunto de cadenas de $\Sigma^*$ aceptadas por $M$

$$\mathcal{L}(M)= \{x \in \Sigma^*: \hat{\delta}(q_0,x)\in F\}$$

Veremos a los automatas finitos como funciones tales que para cada cadena dan un valor booleano: aceptacion o no aceptacion,

$$M:\Sigma^* \rightarrow \{0,1\}$$


### Definicion (automata finito No deterministico (AFND))

Es una 5-upla $<Q,\Sigma, \delta, q_0, F>$ donde

- $Q$ es un conjunto finito de estados

- $\Sigma$ el alfabeto de entrada

- $\delta: Q \times \Sigma \rightarrow \mathcal{P}(Q)$ es la funcion de transicion 

- $q_0 \in Q$ es el estado inicial

- $F \subseteq Q$ es el conjunto de estados finales

### Definicion (funcion de transicion generalizada $\hat{\delta}$)

definimos $\hat{\delta}: Q \times \Sigma^* \rightarrow \mathcal{P}(Q)$,

- $\hat{\delta}(q,\lambda)={q}$

- $\hat{\delta}(q,xa)= \{p \in Q: \exists r \in \hat{\delta}(q,x) \wedge p \in \delta(r,a)\}$ con $x\in \Sigma^*$ y $a \in \Sigma$