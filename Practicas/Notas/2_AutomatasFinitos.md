# Automatas finitos

- Hoy vamos a ver una maquina abstracta que nos permite _reconocer_ lenguajes: los **automatas finitos**
- Estos automatas reconocen exactamente una _calse_ de lenguajes en particular: los **lenguajes regulares**
- Consumen cadenas simbolo por simbolo y mantienen un estado interno.

## Definicion

Un **AFD** (**Automata Finito Deterministico**) es una tupla de la forma 

$$A = \langle Q, \Sigma, \delta, q_0, F \rangle$$

donde:

- $Q$ es un conjunto de estados 

- $\Sigma$ es el alfabeto 

- $\delta: Q \times \Sigma \to Q$ es la funcion de transicion 

- $q_0$ es el estado inicial

- $F \subseteq Q$ es el conjunto de estados finales 

## Configuraciones instantaneas

Como formalizamos que un automata **acepte** una cadena?

- Vamos a definir **configuraciones instantaneas**, una tupla compuesta por el estado actual y lo que resta de consumir de la cadena. Representan una _foto_ del proceso de reconocimiento de una cadena en un instante dado.
- Leguo, el automata va a _transicionar_ entre configuraciones a medida que consume la cadena.

### Formalizando

Dado $A = \langle Q, \Sigma, \delta, q_0, F \rangle$, definimos:

Una **configuracion instantanea** 
$$(q,\alpha) \in Q \times \Sigma^*$$
donde $q$ es el estado actual y $\alpha$ es lo que resta por consumir de la cadena de entrada.

Como podemos fomralizar la transicion entre ellas?
Podemos pasar de un estado a otro consumiendo un simbolo solo si $\delta$ nos dice que existe tal transicion.

**Relacion de transicion entre configuraciones**

$$(q_i, a.\alpha) \vdash_A (q_j, \alpha) \Leftrightarrow \delta(q_i, a) = q_j$$


## Pertenencia al lenguaje

$\alpha$ pertenece al lenguaje aceptado si partiendo de la configuracion inicial $(q_0, \alpha)$ se puede consumir toda la cadena llegando a un estado final.
Es decir, llega a la configuracion $(q_f, \lambda)$ con $q_f \in F$

$$\alpha \in L(A) \Leftrightarrow \exists q_f \in F | (q_0, \alpha) \vdash_A^* (q_f, \lambda)$$


## Estado trampa

Para que el automata quede bien definido, vamos a completarlo con un **estado trampa** (o de _error_), al que van todas las transiciones no definidas y cicla sobre si mismo con todos los simbolos del alfabeto


## Automatas finitos no deterministicos (AFND)

Los automatas que venimos viendo hasta ahora eran **deterministicos**, en cada momento tenian una sola accion posible. $A_3'$ es un automata finito **no deterministico**, que en cada paso puede tener mas de una alternativa para elegir.

Al igual que los AFDs, son una tupla $$ pero cambia la funcion de transicion:

$$\delta : Q \times (\Sigma \cup \lambda) \to \mathcal{P}(Q)$$

- En lugar de un solo estado, devuelve un conjunto.
- Ademas de transiciones por un simbolo de la entrada, podemos transicionar por $\lambda$ sin consumir ningun simbolo.

### Relacion $\vdash$ y lenguaje

Las configuraciones instantaneas son las mismas que para AFDs, pero como es la relacion entre ellas?
Hay dos casos:

Consumiendo un simbolo o por $\lambda$

#### Relacion de transicion entre configuraciones

$$(q_i, a.\alpha) \vdash_A (q_j, \alpha) \Leftrightarrow q_j \in \delta(q_i, a)$$
$$(q_i, \alpha) \vdash_A (q_j, \alpha) \Leftrightarrow q_j \in \delta(q_i, \lambda)$$


## Operaciones en general

#### Union

Dados $A_1$ y $A_2$ automatas finitos, para obtener $L(A_1) \cup L(A_2)$ hay que agregar un nuevo estado inicial con transiciones $\lambda$ a los iniciales de $A_1$ y $A_2$

#### Complemento

Dado un Automata Finito Deterministico **completo**, hay que invertir los finales $F'=F \neg Q$

#### Reversa

Dado un AFND-$\lambda$, obtener $$ tal que:

- $Q' = Q \cup \{q_0'\}$ (nuevo inicial)
- $\delta'(q_0', \lambda) = F$ (arrancar por los finales)
- $q_2 \in \delta'(q_1, a) \Leftrightarrow q_1 \in \delta(q_2,a)$ (dar vuelta las flechas)
- $F' = \{q_0\}$ (terminar con iniciales)