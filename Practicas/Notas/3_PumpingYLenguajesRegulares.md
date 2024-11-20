# Lema de Pumping y lenguajes regulares

- [Lema de Pumping y lenguajes regulares](#lema-de-pumping-y-lenguajes-regulares)
  - [Lenguajes regulares](#lenguajes-regulares)
  - [Lema de pumping](#lema-de-pumping)

| Lenguaje | Automata | normas de produccion de gramaticas |
-----------|----------|------------------------------------|
| recursivamente enumerable | Maquina de Turing |$\alpha A B \to \delta$|
| dependiente del contexto  | Automata linealmente acotado |$\alpha A B \to \alpha \ \beta$|
| recursivamente enumerable | Automata de pila |$A \to \gamma$|
| lenguaje regular | Automata finito |$A \to a y$|


## Lenguajes regulares 

Sean $L_1$ y $L_2$ lenguajes regulares definidos sobre $\Sigma$.

Las siguientes operaciones entre lengujaes (**conjuntos**) preservan la regularidad, (es decir, que siguen siendo lenguajes regulares):

- Union: $L_1 \cup L_2$
- Interseccion: $L_1 \cap L_2$
- Concatenacion: $L_1 . L_2$
- Complemento: $L_1^C = \Sigma \neg L_1$
- Reverso: $L_1^r$

Es mas, para ciertas operaciones con un conjutno finito de lengujaes regulares

Sea $n \in \mathbb{N}$ y $L_1, ..., L_n$ lengujes regulares, sea $L_{nr}$ un lenguje no regular.

- Union finita: $\bigcup^n{i=1} L_i$ es regular
- Interseccion finita: $\bigcap^n_{i=1} L_i$ es regular
- Union disjunta: $L_1 \cup L_{nr}$ es no regular

## Lema de pumping

Sabemos probar que un lenguaje es regular.
Usamos el lema de pumping para probar que un lenguaje NO es regular.

Sea $L$ un lenguaje regular. Existe entonces una longitud minima $p$ tal que, todas las cadenas $\alpha \in L$ que superan o igualan dicha longitud, pueden ser escritas de la forma $\alpha = xyz$ donde 

$$|xy| \leq p, \ |y| \geq 1, \ \forall i \geq 0, xy^iz \in L$$

- Al ser $L$ regular, existe al menos un AFD de estados minimos que lo reconoce. Tomamos $p$ al numero de estados de este automata
- Todas las cadenas $\alpha \in L$ cuya longitud supera al tamaño del automata ($p$) pasan por algun estado al menos dos veces (al menos un ciclo)
- Existe una descomposicion $xyz$ donde $x$ es la parte de la cadena reconocida hasta el 1er estado que se repite, $y$ es la parte de la cadena desde ese estado hasta el siguiente vez que toca el estado, $z$ es el resto
- Para cualquier repeticion de $y$, la cadena resultante ($xz,xyz,xyyz$) va a continuar perteneciendo a $L$ (_pumping_ / _bombeo_)


Llamaremos "pumping" al siguiente consecuente lema

Si $L$ es regular, entonces $L$ cumple "pumping"
Si $L$ NO cumple "pumping", entonces $L$ NO es regular (contrareciproco)

Que $L$ no cumple pumping equivale a probar la siguiente formua es verdadera

$\forall p > 0 (\exists \alpha(\alpha \in L \land |\alpha| \geq p \land \forall x \forall y \forall z (\alpha = xyz \land |xy| \leq p \land |y| \geq 1 \land \exists i \geq 0 (xy^iz \notin L))))$

Para todo $p > 0$

Existe $\alpha$ tal que $\alpha$ pertenece al lenguaje $L$, $|\alpha| \geq p$

Para toda descomposicion $\alpha = xyz$ con $|xy| \leq p$ y $|y| \geq 1$

Existe un $i \geq 0$ tal que $xy^iz \notin L$

1) Me dan un $p > 0$
2) Elijo una cadena $\alpha$ perteneciente a $L$ con longitud mayor o igual a $p$
3) Me dan una descomposicion $\alpha = xyz$ con $|xy| \leq p$ y $|y|\geq 1$
4) Elijo un $i$ mayor o igual a cero tal que $xy^iz$ no pertenezca a $L$

De las cosas que me dan, no puedo asumir mas de lo que se me dice.
De las cosas que elijo, puedo tomar las decisiones que crea convenientes.