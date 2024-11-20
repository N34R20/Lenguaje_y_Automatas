# Gramaticas Libres de Contexto


## definicion de gramatica

## tipos de gramatica

Se clasifican segun la fomra de sus producciones, ya que esto determina su poder  expresivo:

#### Regulares

$P: A \to w | wB$, donde $w \in {V_T}^*$ y $A,B \in V_N$

#### Libres de contexto

$P: A \to \alpha$, donde $\alpha \in (V_T \cup V_N)^*$ y $A \in V_N$

## Derivaciones 

## Lenguaje generado


## Convenciones


## Derivaciones L y R

## Arboles de derivacion

## Para que sirven las Gramaticas Libres de contexto?

- Las gramaticas libres de contexto se suelen usar en los compiladores para describir la sintaxis de lenguajes de programacion.
- Los arboles de derivacion son usados para representar la estructura de los programas.
- Existe una forma automatica de generar a partir de una descripcion de una gramatica un parser, el componente del compilador que descrubre la estrcutura del programa y verifica que sea sintactiamente correcto.
- La gramatica tiene que expresar algo, los arboles que genera tienen que capturar la estructura de la cadena.