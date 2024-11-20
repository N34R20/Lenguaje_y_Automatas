# Funciones computables


- [Funciones computables](#funciones-computables)
  - [El lenguaje $\\mathcal{S}++$](#el-lenguaje-mathcals)
    - [Tesis de Church-Turing](#tesis-de-church-turing)
    - [Variables](#variables)
    - [Instrucciones](#instrucciones)
    - [Programas](#programas)
    - [Funcion computada](#funcion-computada)
    - [Macros](#macros)
  - [Funciones y Lenguajes computables](#funciones-y-lenguajes-computables)
    - [Funciones computables y parcialmente computables](#funciones-computables-y-parcialmente-computables)
    - [Composicion de funciones computables](#composicion-de-funciones-computables)
    - [Funciones primitivas recursivas](#funciones-primitivas-recursivas)
    - [Lenguajes computables](#lenguajes-computables)
  - [Codificacion de programas](#codificacion-de-programas)
  - [SNAP, STEP y programa universal](#snap-step-y-programa-universal)


## El lenguaje $\mathcal{S}++$

Una funcion es cpomputable si puede darse un  un algoritmo que la calcule para cualquier valor de entrada. Sin embargo para formalizar esta idea hayq ue determinar nuestro entendimiento de lo que es un "algoritmo"

### Tesis de Church-Turing

El formalismo de la Maquina de Turing captura de manera completa lo que entendemos por algoritmo, mas precisamente, esto quiere decir que no existen funciones computables para las que no sea posible dar una maquina de Turing.

Existen otros formalismos que son equivalentes a las MT.
Vamos a trabajar con otro: el lenguje de programacion $\mathcal{S}++$

### Variables

En un programa $\mathcal{S}++$ se pueden usar variables de tres tipos:

- Parametros o variables de entrada: $X_1, X_2, X_3$
- Variables locales: $Z_1, Z_2, Z_3$
- Salida: $Y$

### Instrucciones

Sean V una variable y P un programa. Una instruccion de $\mathcal{S}++$ es una de tres tipos:

- Incremento (V++): incrementa el valor de V en 1
- Decremento (V--): decrementa el valor de V en 1 (si es 0, no hace nada)
- Loop (while V $\neq$ 0 do {P}): Ejecutab p minetras V sea distinto de 0
- Instruccion vacia (pass): No hace nada.

### Programas

UN programa es una sucesion de instrucciones. Para hacerlos legibles las escribimos en lineas separadas. Por ejemplo:

$$    P_1:  Z_1++

\\

            Z_1++
\\

            while Z_1 \neq 0 do \{
\\

            Y++
\\

            Z_1--
            
            \}
            $$


    $P_1$:  $Z_1$++

            $Z_1$++

            while $Z_1 \neq 0$ do {

              $Y++$

              $Z_1--$
            
            }

### Funcion computada

Dado un programa $P$, para cada $n \in \mathcal{N}$, se define $\Psi_P^{(n)} : \mathbb{N}^n \to \mathbb{N}$, la **funcion computada** por $P$ con $n$ entradas.

### Macros


## Funciones y Lenguajes computables

### Funciones computables y parcialmente computables

### Composicion de funciones computables

### Funciones primitivas recursivas

### Lenguajes computables


## Codificacion de programas

## SNAP, STEP y programa universal