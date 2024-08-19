# Teoria de Automatas

La teoría de autómatas es una rama de la teoría de la computación que estudia las máquinas abstractas y los problemas que éstas son capaces de resolver. La teoría de autómatas está estrechamente relacionada con la teoría del lenguaje formal ya que los autómatas son clasificados a menudo por la clase de lenguajes formales que son capaces de reconocer. También son de gran utilidad en la teoría de la complejidad computacional.

Un autómata es un modelo matemático para una máquina de estado finito (FSM sus siglas en inglés). Una FSM es una máquina que, dada una entrada de símbolos, "salta" a través de una serie de estados de acuerdo a una función de transición (que puede ser expresada como una tabla). En la variedad común "Mealy" de FSMs, esta función de transición dice al autómata a qué estado cambiar dados unos determinados estado y símbolo.

La entrada es leída símbolo por símbolo, hasta que es "consumida" completamente (piense en ésta como una cinta con una palabra escrita en ella, que es leída por una cabeza lectora del autómata; la cabeza se mueve a lo largo de la cinta, leyendo un símbolo a la vez) una vez la entrada se ha agotado, el autómata se detiene.

Dependiendo del estado en el que el autómata finaliza se dice que este ha aceptado o rechazado la entrada. Si este termina en el estado "acepta", el autómata acepta la palabra. Si lo hace en el estado "rechaza", el autómata rechazó la palabra, el conjunto de todas las palabras aceptadas por el autómata constituyen el lenguaje aceptado por sí mismo.

## Vocabulario

Los conceptos básicos de símbolos, palabras, alfabetos y strings son comunes en la mayoría de las descripciones de los autómatas. Estos son:

- **Símbolo**:

    Un dato arbitrario que tiene algún significado o efecto en la máquina. A estos símbolos también se les llama "letras" o "átomos".1​

- **Palabra**:

    Una cadena finita formada por la concatenación de un número de símbolos.

- **Alfabeto**:

    Conjunto finito de símbolos. Un alfabeto se indica normalmente con $\sum$, que es el conjunto de letras en un alfabeto.

- **Lenguaje**:

    Un conjunto de palabras, formado por símbolos en un alfabeto dado. Puede ser infinito.

- **Clausura de Kleene**:
    
    Un lenguaje se puede considerar como un subconjunto de todas las posibles palabras. El conjunto de todas las palabras puede, a su vez, ser considerado como el conjunto de todas las posibles concatenaciones de cadenas. Formalmente, este conjunto de todas las cadenas se llama en inglés free monoid. Se indica como $\sum^*$, y el superíndice * se llama la estrella de Kleene.

## Automatas Finitos
Formalmente, un autómata finito (AF) puede ser descrito como una 5-tupla 
$⟨Q, \Sigma, \delta, S_0, F⟩$

Existen tres tipos de autómatas finitos

### Automata finito determinista (AFD)

### Automata finito no determinista (AFND)

### Automata finito no determinista con transiciones $\epsilon$ (AFND-$\epsilon$)


Sin embargo, puede observarse que todos estos tipos de autómatas **pueden aceptar los mismos lenguajes**. Siempre se puede construir un AFD que acepte el mismo lenguaje que el dado por un AFND

## Extensiones a los autómatas finitos