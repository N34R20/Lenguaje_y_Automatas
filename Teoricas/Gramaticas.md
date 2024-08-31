# Gramaticas

## Alfabetos y lenguajes

Un alfabeto es un conjunto finito, no vacio, de simbolos

Consideramos la concatenacion de simbolos

Una palabra sobre el alfabeto $\Sigma$ es una secuencia finita de elementos (cero o mas) de un alfabeto. Tmabien lo llamamos palabras o strings

palabra nula $\lambda$. No tiene simbolos

- Ejemplos: Estas son algunas palabras sobre $\Sigma = \{a,j,r\}$, $a, j, aa, aj, ar, ja, jj, aaj, rja, raja, jarra$, etc.

## EL conjunto de todas las palabras sobre un alfabeto

Dado un alfabeto $\Sigma$, la clausura de Kleene del alfabeto $\Sigma$, que denotamos $\Sigma^*$ se define asi:

- $\Sigma^0 = \{\lambda\}$

- $\Sigma^1 = \Sigma = \{a : a\in \Sigma\}$

- $\Sigma^2 = \Sigma\Sigma = \{ab : a\in \Sigma\, b\in \Sigma\}$

...

- $\Sigma^* = \bigcup_{i \geq 0} \Sigma^i$

Cual es la cardinalidad del conjunto $\Sigma^i$?

El conjunto $\Sigma$ tiene $|\Sigma|$ elementos.
Para cada $i \geq 0$, se tiene $|\Sigma|^i$ palabras.
El conjunto $\Sigma^*$ tiene una cantidad infinita numerable de palabras.

## Clausura positiva

$$\Sigma^+ = \bigcup_{i \geq 1} \Sigma^i$$

## Hay tantas palabras como numeros naturales

### Teorema

$|\Sigma^*|$ es igual a la cardinalidad de $\N$

Un orden entre pares de elementos es una relacion antisimietrica y transitiva.

### Definicion (Orden logitud-lexicografico en $\Sigma^*$)

Definimos el orden $\prec \subset \Sigma^* \times \Sigma^*$

Asumimos un orden lexicografico entre los elementos del alfabeto.
Lo extendemos a un lexicografico entre todas las palabras de la misma logitud.
Las palabras de menor logitud son menores que las de mayor logitud.
Por ejemplo para $\Sigma = \{a,b,c\}$

$\lambda \prec a \prec b \prec c \prec aa \prec ab \prec ac \prec ba \prec bb \prec bc$

### Demostracion del Teorema

Definimos una biyeccion $f: \N \rightarrow \Sigma^*, f(i) =$ la i-esima palabra en el orden $\prec$ longitud lexografico sobre $\Sigma^*$.

## Lenguaje sobre un alfabeto

Un lengujae L sobre un alfabeto $\Sigma$ es un conjunto de palabras sobre $\Sigma$.

Es decir, $L \subseteq \Sigma^*$

Ejemplos:

- $\emptyset$
- $\{\lambda\}$ (notar que es distinto de $\emptyset$)
- $\{0,01,011,0111,01111,....\}$, es un lenguaje sobre $\Sigma = \{0,1\}$

## Cuantos lenguajes hay?

### Definicion

Si $A$ es un conjunto, $\mathcal{P}(A)$ es el conjunto de todos los subconjuntos de $A$, $\mathcal{P}(A) = \{ B \subseteq A \}$

Si $A$ es un conjutno finito, entonces $|\mathcal{P}(A)| = 2^{|A|}$

- Ejemplo: $A=\{a,b,c\}$ entonces $|\mathcal{P}(A)|=2^3$,
    $\mathcal{P}(A) = \{\}$

- Ejemplo:

## La cantidad de lengujaes es no numerable

## Lenguaje formales y su tratamiento computacional

¿Todos los lenguajes se pueden reconocer/generar computacionalmente?
¿Cuál es la diﬁcultad computacional?

## Que es una computadora?

Un autómata es un dispositivo que realiza pasos mecánicamente o
electrónicamente, de manera autómatica.

Vistos como modelos de cómputo, hay autómatas con distintas capacidades.

autómatas ﬁnitos
autómatas de pila
máquinas de Turing
maquinas probabilsíticas
máquinas cuánticas

y hay más

A lo largo del curso deﬁniremos los 3 primeros de la lista y mostraremos su capacidades.

¿Cuántos autómatas hay?
Tan solo una cantidad numerable, ya que son deﬁnidos ﬁnitariamente.
Se los puede ver a todos como programas

## ¿Todos los lenguajes se tratan computacionalmente?

No todos. Solamente una cantidad numerable.
Hay una cantidad no numerable de lenguajes ($|\mathcal{P}(\Sigma^*)|$) y hay tan solo una cantidad numerable de procedimientos computacionales.
Los estudaremos según la jerarquía de Chomsky, que se corresponde con
una jerarquía de los autómatas capaces de reconocerlos.

## Relaciones

## Composicion de relaciones

## Relacion potencia

## Clausura transitiva

## Demostracion de la proposicion

## La jerarquia de Chomsky (Noam Chomsky en 1956)

Es una clasiﬁcación jerárquica de tipos de gramáticas formales que generan lenguajes formales

![](/imgs/Chomsky1.png)

#### Jerarquia de Chomsky

![](/imgs/jerarquiaChomsky.png)

## Gramaticas

#### Definicion

#### Ejemplo

## Lenguaje generados por una gramatica

#### Definicion

#### Ejemplo

#### Definicion

#### Definicion

## Clausura de Kleene de la relacion de derivacion $\rightarrow_G $

## La Jerarquia de Chomsky

## Arbol de derivacion gramaticas libres de contexto (y regulares)

## Ejemplo árbol de derivación y derivación más a la izquierda

![](/imgs/arbol1.png)

## Lema crucial

### Demostracion

## Lenguajes formales y complejidad computacional

![](/imgs/JerarquiaYComplejidad.png)
