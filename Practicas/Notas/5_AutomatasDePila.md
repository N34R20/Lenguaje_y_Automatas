# Automatas de Pila

- [Automatas de Pila](#automatas-de-pila)
  - [Introduccion](#introduccion)
    - [Lenguajes regulares](#lenguajes-regulares)
    - [Lenguajes libres del contexto](#lenguajes-libres-del-contexto)
  - [Automatas de Pila](#automatas-de-pila-1)
    - [Definicion](#definicion)
    - [Definicion de transicion](#definicion-de-transicion)
  - [Configuracion instantanea](#configuracion-instantanea)
  - [Lenguaje aceptado](#lenguaje-aceptado)
    - [Lenguaje aceptado por pila vacia:](#lenguaje-aceptado-por-pila-vacia)
    - [Lenguaje aceptado por estado final](#lenguaje-aceptado-por-estado-final)
  - [Automata de pila deterministico](#automata-de-pila-deterministico)
  - [Existe equivalencia entre APD y APND?](#existe-equivalencia-entre-apd-y-apnd)
  - [Cosas importantes](#cosas-importantes)

## Introduccion


### Lenguajes regulares

- Son los mas simples, el tipo 3 de la jerarquia de Chomsky
- Reconocidos por automatas finitos / expresiones regualres (son formalismos equivalentes)
- No tienen memoria (no pueden contar, salvo que se requieran esatdos finitos)
- Lema de pumping para demostrar que un lenguaje no es regular

### Lenguajes libres del contexto

- Tipo 2 de la jerarquia de Chomsky
- Reconocidos por automatas de pila y gramaticas libres de contexto
- Mayor poder expresivo, la pila permite tener memoria y poder contar (algunas cosas)

## Automatas de Pila

- La pila es una cadena de simbolos
- Las transiciones pueden depender del simbolo en el tope de la pila, ademas del primer simbolo de la cadena de entrada.
- En cada transicion se desapila el simbolo del top y se puede apilar una cadena

### Definicion

$$M = \langle Q,\Sigma, \Gamma, \delta, q_0, Z_0, F \rangle$$

Donde:

- $Q$: es un conjunto finito de estados 
- $\Sigma$: es el alfabeto de entrada 
- $\Gamma$: es el alfabeto de pila
- $q_0 \in Q$: es el estado inicial 
- $Z_0 \in \Gamma$: es el simbolo inicial de la pila 
- $F \subseteq Q$: es el conjunto de estados finales 
- $\delta$: es la funcion de transicion: $Q \times (\Sigma \cup \{\lambda\}) \times \Gamma \to P(Q \times \Gamma^*)$

### Definicion de transicion

$a, Z / A$

- $a$: Simbolo de la entrada que se consume
- $Z$: Simbolo del tope dde la pila que desapilo
- $A$: Cadena que apilo en la pila

## Configuracion instantanea

En un automata finito, teniamos como configuracion instantanea un elemento de $Q \times \Sigma^*$

donde $q$ es el estado actual y es lo resta por consumir de la cadena de entrada

Como sera una configuracion instantanea en un automata de pila?
$$(q,\alpha, \gamma) \in Q \times \Sigma^* \times \Gamma^*$$

donde:
- $q$ es el estado actual
- $\alpha$ es la cadena de entrada que resta consumir
- $\gamma$ es el contenido de la pila

## Lenguaje aceptado 

Relacion de transicion entre configuraciones:
$\forall q_1, q_2 \in Q, a \in \Sigma^*, b \in \Gamma, \beta \in \Gamma^*$:
- $(q_1, a \alpha, b \gamma) \vdash (q_2, \alpha, \beta \gamma) \Leftrightarrow (q_2, \beta) \in \delta(q_1, a, b)$
 
- $(q_1, \alpha, b \gamma) \vdash (q_2, \alpha, \beta \gamma) \Leftrightarrow (q_2, \beta) \in \delta(q_1, \lambda, b)$

Notar que _siempre_ se saca el tope de la pila. Si en una transicion no se quiere modificar la pila hay que volver a apliar el mismo simbolo.

### Lenguaje aceptado por pila vacia:

$$\alpha \in N(M) \Leftrightarrow \exists q_n \in Q | (q_0, \alpha, Z_0) \vdash^* (q_n , \lambda, \lambda)$$

Se acepta una cadena si existe una secuencia de trasniciones por medio de la cual se consume toda la cadena dejando la pila vacia.


### Lenguaje aceptado por estado final

$$\alpha \in L(M) \Leftrightarrow \exists q_f \in F , \gamma \in \Gamma^* | (q_0, \alpha, Z_0) \vdash^* (q_f , \lambda, \gamma)$$

notar que en este caso nos importa en que esatdo termina y lo que contiene la pila nos deja de importar.


## Automata de pila deterministico

Un automata de pila es deterministico si $\forall q \in Q, z \in \Gamma, a \in \Sigma$ vale que:

- $|\delta(q, a , z)| \leq 1$
- $|\delta(q, \alpha, z)| \leq 1$
- $|\delta(q, \alpha, z)| = 1 \Rightarrow |\delta(q, a , z)| = 0$


## Existe equivalencia entre APD y APND?

Existen leguajes independientas del contexto que no son generados por nigun APD. Esto implica que, a diferencia de los autromatas finitos, no existe una equivalencia entre los Automata de pila deterministicos y los no deterministicos.

Los lenguajes generados por APD por pila vac´ıa son libres
de prefijos. Es decir, si $\alpha \in L$ entonces $\forall \beta \neq \lambda, \alpha \beta \notin L$

Concluimos que los lenguajes geenrados por APD por pila vacia no son equivalentes a los lenguajes generados por APD por estados finales.

## Cosas importantes 

- Los lenguajes libres de contexto tienen mayor poder expresivo que los lenguajes regulares, pueden contar ciertas cosas.
- Los automatas de pila por estado final aceptan una cadena si la misma se puede consumir en su totalidad y al finalizar se llega a un estado fianl, sin importar el esatdo de la pila.
- Los automatas de pila por pila vacia aceptan una cadena si la misma se peude consumir en su totalidad y si al finalizar se llega la pila esta vacia, sin importar enq ue esatdo esta.
- Los lenguajes generados por APND tienen mayor poder expresivo que los APD
- Los lenguajes generados por APND por esatdo final tienen mayor poder expresivo que los APND por pila vacia
- Los lenguajes generados por APD por esatdo final tienen mayor poder expresivo que los APD por pila vacia
- Los lenguajes generados por APD por pila vacia son libres de prefijos