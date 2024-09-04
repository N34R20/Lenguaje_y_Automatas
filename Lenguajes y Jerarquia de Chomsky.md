### Lenguaje (en el contexto de la teoría de lenguajes formales)
Un **lenguaje** es un conjunto de cadenas formadas a partir de un alfabeto. El alfabeto es un conjunto finito de símbolos, y una cadena es una secuencia finita de símbolos de ese alfabeto. Los lenguajes pueden ser finitos o infinitos.

#### Ejemplo:
- Alfabeto: $\Sigma = \{a, b\}$
- Lenguaje: $L = \{ab, aab, bb\}$

En este ejemplo, $L$ es un lenguaje formado por las cadenas "ab", "aab" y "bb".

### Jerarquía de Chomsky
La **Jerarquía de Chomsky** es una clasificación de los lenguajes formales en cuatro tipos diferentes según el poder de las gramáticas que los generan. Cada nivel de la jerarquía es más inclusivo que el anterior:

1. **Tipo 0: Lenguajes Recursivamente Enumerables (Gramáticas no restringidas)**
   - **Definición**: Son los lenguajes que pueden ser reconocidos por una máquina de Turing. Las gramáticas correspondientes no tienen restricciones sobre la forma de las reglas de producción.
   - **Ejemplo**: Cualquier lenguaje generado por una máquina de Turing es un lenguaje recursivamente enumerable.

2. **Tipo 1: Lenguajes Contextuales (Gramáticas Sensibles al Contexto)**
   - **Definición**: Son los lenguajes que pueden ser generados por gramáticas donde las reglas de producción son de la forma $\alpha A \beta \rightarrow \alpha \gamma \beta$, donde $A$ es un no terminal, y $\alpha$, $\beta$, y $\gamma$ son cadenas de símbolos, con la restricción de que la longitud de $\gamma$ no puede ser menor que la longitud de $A$.
   - **Ejemplo**: Un lenguaje que requiere que el número de símbolos $a$ sea igual al número de símbolos $b$ (por ejemplo, $\{a^n b^n c^m \mid n, m \geq 1\}$) es un ejemplo de un lenguaje contextual.

3. **Tipo 2: Lenguajes Independientes del Contexto (Gramáticas Libres de Contexto)**
   - **Definición**: Son los lenguajes generados por gramáticas donde cada regla de producción es de la forma $A \rightarrow \gamma$, donde $A$ es un no terminal y $\gamma$ es una cadena de terminales y no terminales.
   - **Ejemplo**: El lenguaje de paréntesis balanceados $\{ (^{n} )^{n} \mid n \geq 1\}$ es un ejemplo clásico de un lenguaje independiente del contexto.

4. **Tipo 3: Lenguajes Regulares (Gramáticas Regulares)**
   - **Definición**: Son los lenguajes que pueden ser generados por gramáticas donde las reglas de producción son de la forma $A \rightarrow aB$ o $A \rightarrow a$, donde $A4 y $B$ son no terminales, y $a$ es un terminal. Estos lenguajes pueden ser reconocidos por autómatas finitos.
   - **Ejemplo**: El lenguaje $\{a^n b^m \mid n, m \geq 0\}$, que incluye cadenas como "a", "ab", "aabb", etc., es un lenguaje regular.

### Resumen visual de la Jerarquía de Chomsky:

- **Tipo 3** ⊆ **Tipo 2** ⊆ **Tipo 1** ⊆ **Tipo 0**

Cada tipo de lenguaje es un subconjunto del tipo superior en la jerarquía. Por ejemplo, todos los lenguajes regulares son también lenguajes libres de contexto, pero no todos los lenguajes libres de contexto son regulares.