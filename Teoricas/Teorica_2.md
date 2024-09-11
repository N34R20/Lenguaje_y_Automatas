# Teorica 2 - Automatas finitos y Gramaticas Regulares

## Temas 

- **Definicion**: Automata finito deterministico

- **Definicion**: Automata finito no deterministico

- **Teorema**: Para todo AFND hay un AFD que reconoce el mismo lenguaje

- **Teorema**: Para cada gramática regular hay un AFND que acepta el lenguaje generado por la gramática

- **Teorema**: Para cada AFD hay una gramática que genera el mismo lenguaje que el acpetado por el AFD

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

- $\hat{\delta}(q,\lambda)= \{q\}$

- $\hat{\delta}(q,xa)= \{p \in Q: \exists r \in \hat{\delta}(q,x) \wedge p \in \delta(r,a)\}$ con $x\in \Sigma^*$ y $a \in \Sigma$

### Definicion (lenguaje aceptado por un AFND)

El lenguaje aceptado por un AFND $M=<Q,\Sigma, \delta, q_0, F>$, al que denotaremos $\mathcal{L}(M)$, es el conjunto de cadenas de $\Sigma^*$ aceptadas por $M$,

$$\mathcal{L}(M)= \{x \in \Sigma^*: \hat{\delta}(q_0,x) \cap F \neq \emptyset \}$$

Podemos extender la funcion de transicion aún más, haciendo que mapee conjuntos de estados y cadenas en conjutnos de estados.

### Definicion (funcion de transicion de conjuntos de estados)

Funcion de transicion $\delta: \mathcal{P}(Q) \times \Sigma^* \rightarrow \mathcal{P}(Q)$ dada por 

$$\delta(P,x) = \bigcup_{q \in P} \delta(q,x)$$

Es trivial ver que, para todo AFD existe un AFND equivalente.
Lo que no es tan obvio es que lo recíproco también es cierto:
para cada AFND existe un AFD equivalente

### Teorema (Equivalencia entre AFND y AFD)

Dado un AFND $M =\langle Q, \Sigma, \delta, q_0, F \rangle$, existe un AFD $M' =\langle Q', \Sigma, \delta', q_0', F' \rangle$ tal que $\mathcal{L}(M) = \mathcal{L}(M')$

Recordemos que una gramática $G = \langle  V_N , V_T , P, S \rangle$ es regular si todas las producciones son de la forma $A \rightarrow \lambda$ , o $A \rightarrow a$, o $A \rightarrow aB$.

### Teorema
Dada una gramática regular $G = \langle  V_N , V_T , P, S \rangle$ existe un AFND $M = \langle Q, \Sigma, \delta, q_0, F \rangle$ tal que $\mathcal{L}(G) = \mathcal{L}(M)$



### Teorema

Dado un AFD $M = \langle Q, \Sigma, \delta, q_0, F \rangle$〉 existe una gramática regular $G = \langle  V_n , V_T , P, S \rangle$ tal que $\mathcal{L}(G) = \mathcal{L}(M)$
