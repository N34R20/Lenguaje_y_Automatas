# Expresiones regulares y conversiones


- [Expresiones regulares y conversiones](#expresiones-regulares-y-conversiones)
  - [Expresiones regulares](#expresiones-regulares)
    - [Como se definen](#como-se-definen)
    - [Lenguaje denotado por una expresion regular](#lenguaje-denotado-por-una-expresion-regular)
    - [Precedencia](#precedencia)
    - [Observaciones](#observaciones)
    - [Propiedades](#propiedades)
  - [Conversion de AF a ER](#conversion-de-af-a-er)
    - [resumen](#resumen)
    - [Repaso de automatas finitos](#repaso-de-automatas-finitos)
    - [Intuicion sobre conversion AF a ER](#intuicion-sobre-conversion-af-a-er)
    - [Lenguaje aceptado por un estado](#lenguaje-aceptado-por-un-estado)
    - [Lema de Arden](#lema-de-arden)
    - [Formalizacion](#formalizacion)
      - [Generalizacion del sistema aceptado](#generalizacion-del-sistema-aceptado)
      - [Ecuaciones](#ecuaciones)
      - [Ecuaciones entre lenguajes](#ecuaciones-entre-lenguajes)
  - [Conversion de ER a AF](#conversion-de-er-a-af)
    - [Resumen](#resumen-1)
    - [Intuicion](#intuicion)
    - [Derivada de un lenguaje](#derivada-de-un-lenguaje)
    - [Derivada de una ER](#derivada-de-una-er)
      - [Derivada de una ER segun su estructura](#derivada-de-una-er-segun-su-estructura)
    - [Porque las derivadas nos dan las transiciones?](#porque-las-derivadas-nos-dan-las-transiciones)
    - [Armado del automata](#armado-del-automata)


## Expresiones regulares

Las expresiones regulares se utilizan para _denotar_ o _definir_ **lenguajes regulares**, al igual que los automatas finitos

### Como se definen

- $\emptyset$
- $\lambda$
- $a$ (para cada $a \in \Sigma$)

Si $R$ y $S$ son expresiones regulares, entonces:

- $L(R).L(S)$: (Concatenacion)
- $R|S$: (Union)
- $R^*$: (Clausura de Kleene)
- $R^+$: (Clausura de positiva)

Tambien son expresiones regulares.

### Lenguaje denotado por una expresion regular

Cada expresion regular $E$ va a denotar un lenguaje regular $L(E)$.

Sea $a \in \Sigma$ un simbolo y $R$ y $S$ expresiones regulares

| Nombre               |  E  |  L(E)  |
|----------------------|-----|--------|
| Vacio                |  $\emptyset$ |   $\emptyset$   |
| Cadena vacia         |  $\lambda$ |   $\{\lambda\}=$   |
| Simbolo              |  $a$ |   $\{a\}$   |
| Concatenacion        |  $R.S$ |   $L(R).L(S)$   |
| Union                |  $R/S$ |   $L(R) \cup L(S)$   |
| Clausura de Kleene   |  $R^*$ |   $(L(R))^*$   |
| Clausura de Positiva |  $R^+$ |   $L(R.R^*)$   |

### Precedencia

### Observaciones

- EL poder expresivo de las ER y los AF son el mismo (lenguajes regulares), pero a veces un formalismo es mas intuitivo que otro

- Es mas facil trabajar complemento, iniciales, finales, subcadenas en un AFs que en ERs


### Propiedades

- Conumtatividad de | : $u|v = v|u$

- Distributividad de . respecto de | : $u(v|w) = uv|uw$

- Elemento neutro de . : $u.\lambda = \lambda.u = u$

- Elemento absorbente de . : $u.\emptyset = \emptyset.u = \emptyset$

- Elemento neutro de | : $$u|\emptyset = \emptyset|u = u$$

## Conversion de AF a ER

### resumen

Para hacer la conversion de Af a ER queremos encontrar una expresion cerrada que denote $L_0=L$. 
Para ello,

- Planteamos el sistema de equaciones:

$$L_i = a_1.L_{k_1} | ... | a_m . L_{k_m} | \epsilon(L_i)$$

  Donde $\epsilon(L_i) = \lambda$ si $L_i$ es final y $\emptyset$ si no.

- Lo resolvemos llevando las equaciones a una forma que nos permita aplicar el Lema de Arden.

- Terminamos al ecnotrar una expresion cerrada para $L_0$

### Repaso de automatas finitos

### Intuicion sobre conversion AF a ER

- Tenemos L, el conjunto de cadenas aceptadas partiendo de $q_0$
- Vamos a pensar a $L_i$ como el lenguaje aceptado partiendo del estado $q_1$
- Queremos denotar cada uno con una expresion regular
- De esa forma, la ER que denote $L_0 = L(A)$ va a denotar el lenguaje que acepta el automata



### Lenguaje aceptado por un estado

### Lema de Arden

Sea $R$ un lenguaje, y $\alpha , \beta$ expresiones regulares sobre $\Sigma$,

Si $R = \alpha.R | \beta$ y $\lambda \notin L(\alpha)^a$, entonces $R = \alpha^*.\beta$

Intuicion: $\alpha$ es el caso recursivo y $\beta$ el caso base.

### Formalizacion 

#### Generalizacion del sistema aceptado

De la misma forma que definimos el lenguaje $L$ como el conjunto de cadenas aceptadas por el automata partiendo del estado $q_0$,

$$L(A) = \{ \alpha \in \Sigma | \exists q_f \in F: (q_0, \alpha) \models^* (q_f, \lambda)\}$$

para cada esatdo $q_i$ podemos definir un lenguaje $L_i$ que corresponda al conjunto de cadenas aceptadas partiendo de el

$$L_i = \{ \alpha \in \Sigma | \exists q_f \in F: (q_i, \alpha) \models^* (q_f, \lambda) \}$$


#### Ecuaciones

Queremos una forma de caracterizar el lenguaje generado por cada
estado $q_i$, con una expresion regular.
Consideremos las siguientes igualdades para un estado $q_i$ y $\Sigma = \{a_1,...,a_m \}$

$\delta(q_i,a_1) = q_{k_1}$
$\delta(q_i,a_2) = q_{k_2}$
            .
            .
            .
$\delta(q_i,a_m) = q_{k_m}$

A partir de estas ecuaciones , podemos expresar al lenguaje $L_i$ mediante la siguiente ecuacion.

$$L_i = a_1.L_{k_1} | ... | a_m . L_{k_m} | \epsilon(L_i)$$

donde

$$\epsilon(L) = \begin{cases} 
\emptyset & \text{si } \lambda \notin L \\
\{\lambda\} & \text{si } \lambda \in L
\end{cases}$$


#### Ecuaciones entre lenguajes



## Conversion de ER a AF

### Resumen

Para hacer la convercion de una ER a AF, 

- Tomamos como el estado inicial a R
- Para cada esatdo nuevo (que tmb sera una Expresion regular), lo hacemos transicionar por todos los simbolos del alfabeto usando las derivadas
- Tomamos como estados finales aquellas ER que acepten $\lambda$, osea que $\lambda \in L(Q)$

### Intuicion

- Queremos formular un metodo para el camino inverso: dada una expresion regular, construir un automata que acepte el mismo lenguaje.
- La idea sera interpretar a las expresiones regulares como estados que nos indican que cadenas se aceptan partiendo de ellos. Las transiciones corresponderan a hacerlas "consumir" un simbolo del alfabeto, dando como resultado otra expresion regular que acepta lo que resta

### Derivada de un lenguaje

Definicion:

Sea $L$ un lenguaje sobre un alfabeto $\Sigma$ y sea $a \in \Sigma$ un simbolo del alfabeto, entonces la derivada de $a$ respecto de $L$ es 

$$\partial a (L) = \{\alpha | \alpha \in \Sigma \text{ tal que } a \alpha \in L\}$$


### Derivada de una ER

- De la misma manera que definimos una derivada respecto de un lenguaje, la podemos definir respecto de una expresion regular.
- Si $R$ es una expresion regular, entonces $\partial a (R)$ es otra expresion regular que denota a $\partial a (L(R))$
- Dada una expresion regular $R$, la derivada $\partial a (R)$ nos dice a cual expresion regular transiciona luego de consumir $a$.
- Vamos a definirla recursivamente sobre la estructura de la expresion regular.

#### Derivada de una ER segun su estructura

Para $a \in \Sigma$,

$$\partial a(\emptyset) = \emptyset$$

$$\partial a(\lambda) = \emptyset$$

$$\partial a(b) = \begin{cases} 
\emptyset & \text{si } a \neq b \\
\lambda & \text{si } a = b
\end{cases}$$

Si $R,S$ son expresiones regulares,

$$\partial a (R|S) = \partial a (R) | \partial a (S)$$

$$\partial a (R.S) = \partial a (R).S | \epsilon(R).\partial a (S)$$

$$\partial a (R^*) = \partial a (R).R^*$$

$$\text{donde }\epsilon (R) = \begin{cases} 
\emptyset & \text{si } \lambda \notin L \\
\lambda & \text{si } \lambda \in L
\end{cases}$$

### Porque las derivadas nos dan las transiciones?

### Armado del automata

Una vez que tenemos las derivadas calculadas, podemos construir
el automata correspondiente:

- Los estados finales son las expresiones regualres $L_i$
- $\delta(L_i, a) = L_j$, si $\partial a(L_i) = L_j$
- Son esatdos finales los $L_i$ tales que $\lambda \in L_i$