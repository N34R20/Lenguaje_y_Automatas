# Lenguajes

- Un **alfabeto** es un conjunto finito de simbolos

- Una **cadena** es una secuencia finita de simbolos de un alfabeto

- Usamos la notacion $\lambda$ para denotar una cadena que no contiene simbolos
    - $\lambda$ no es un simbolo del alfabeto, es un _meta-simbolo_.

- Dado un alfabeto $\Sigma$, podemos pensar que una cadena sobre el de longitud $n$ es una **tupla** de $n$ elementos de $\Sigma$

- Usamos la notacion $\Sigma^n$ para denotar el conjutno de todas las cadenas de longitud $n$ sobre $\Sigma$, la $n$-esima **potencia** de $\Sigma$

- La **clausura de Kleene** de un alfabeto $\Sigma^*$ es el conjuto $\Sigma$ de todas las cadenas sobre $\Sigma$

    $$\Sigma^* = \bigcup_{i \geq 0} \Sigma^i$$

- La **clausura positiva** de un alfabeto $\Sigma^+$ es el conjunto $\Sigma$ de todas las cadenas _no vacias_ sobre $\Sigma$

    $$\Sigma^+ = \bigcup_{i \geq 1} \Sigma^i$$


## Concatenacion de cadenas

- La operacion basica para operar con cadenas es la concatenacion

Dadas $\alpha, \beta \in \Sigma^*$ dos cadenas, su concatenacion es una cadena 
$$\alpha.\beta \in \Sigma^*$$ 
que contiene a los simbolos de $\alpha$ seguidos por los simbolos de $\beta$

### Propiedades

- Es Asociativa 
- No es conmutativa
- Tiene elemento neutro

## Estructura recursiva de las cadenas

- Si fijamos un alfabeto $\Sigma$, todas las cadenas de $\Sigma^*$ corresponden a uno de estos dos casos:
  1) $\lambda$: la cadena vacia
  2) $x.\alpha$: donde $x \in \Sigma$ y $\alpha \in \Sigma$

- Esto es util para:
  - Definir funciones de manera recursiva
  - Demostrar propiedades usando **recursion estructural**


## Longitud de una cadena

## Cantidad de apariciones

## Potencia de cadenas

## Reversa

## Lenguajes

## Union de lenguajes

## Interseccion de lenguajes

## Complemento de un lenguaje

## Concatenacion de lenguajes

### Propiedades

## Potencia de un lenguaje

##

## Reverso de un lenguaje

## Prefijos, sufijos y subcadenas

Dado un lenguaje $L$,

- El lenguaje de sus **prefijos**, $Ini(L)$ se obtiene quitando cero o mas simbolos del final de las cadenas de $L$

    $$Ini(L) = \{ \alpha \in \Sigma^* | \exists \beta \in \Sigma^* \text{ tal que } \alpha \beta \in L \}$$

- El lenguaje de sus **sufijos**, $Fin(L)$ se obtiene quitando cero o mas simbolos del principio de las cadenas de $L$

    $$Fin(L) = \{ \alpha \in \Sigma^* | \exists \beta \in \Sigma^* \text{ tal que } \beta \alpha \in L \}$$
 
- El lenguaje de sus **subcadenas**, $Sub(L)$ se obtiene quitando cero o mas simbolos del principio y del final de las cadenas de $L$

    $$Sub(L) = \{ \alpha \in \Sigma^* | \exists \beta , \gamma \in \Sigma^* \text{ tal que } \beta \alpha \gamma \in L \}$$