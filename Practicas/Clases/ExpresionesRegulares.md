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
    - [Formalizacion - Generalizacion del sistema aceptado](#formalizacion---generalizacion-del-sistema-aceptado)
  - [Conversion de ER a AF](#conversion-de-er-a-af)
    - [Resumen](#resumen-1)
    - [Intuicion](#intuicion)
    - [Derivada de un lenguaje](#derivada-de-un-lenguaje)
    - [Derivada de una ER](#derivada-de-una-er)
    - [Estructura de ER](#estructura-de-er)
    - [Porque las derivadas nos dan las transiciones?](#porque-las-derivadas-nos-dan-las-transiciones)
    - [Armado del automata](#armado-del-automata)


## Expresiones regulares

Las expresiones regulares se utilizan para _denotar_ o _definir_ **lenguajes regulares**, al igual que los automatas finitos

### Como se definen

### Lenguaje denotado por una expresion regular

### Precedencia

### Observaciones

### Propiedades

## Conversion de AF a ER

### resumen

### Repaso de automatas finitos

### Intuicion sobre conversion AF a ER

### Lenguaje aceptado por un estado

### Lema de Arden

### Formalizacion - Generalizacion del sistema aceptado

## Conversion de ER a AF

### Resumen

Para hacer la convercion de una ER a AF, 

- Tomamos como el estado inicial a R
- Para cada esatdo nuevo (que tmb sera una Expresion regular), lo hacemos transicionar por todos los simbolos del alfabeto usando las derivadas
- Tomamos como estados finales aquellas ER que acepten $\lambda$, osea que $\lambda \in L(Q)$

### Intuicion

### Derivada de un lenguaje

### Derivada de una ER

### Estructura de ER

### Porque las derivadas nos dan las transiciones?

### Armado del automata