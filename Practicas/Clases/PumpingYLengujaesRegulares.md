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

