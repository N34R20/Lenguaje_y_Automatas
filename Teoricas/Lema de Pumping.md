# Lema de "Pumping" (Bombeo)

Sea $L$ un lenguaje regular. Existe una longitud $n$ tal que para toda $z \in L$ con $|z| \geq n$ existe $u,v,w \in \Sigma^*$ tales que 

- $ z = uvw, $
- $ |uv| \leq n, $
- $ |v| \geq 1,$

Entonces $ \forall i \geq 0, uv^i w \in L $

### Ejemplo

$L=\{a^k b^k : k \geq 0\}$ sobre $\Sigma = \{a,b\}$ no es regular.


### Demostracion

### Ejemplo

$L=\{0^{k^2} : k \geq 1\}$ sobre $\Sigma = \{0\}$ no es regular.


### Demostracion

### Ejemplo

$L=$\{$w : w$ tiene la misma cantidad de 0s que de 1s\}  no es regular.


### Demostracion


## Definicion: Configuracion instantanea de un AFD

## Definicion: Transicion entre configuraciones instantaneas $\vdash$


## Lema

Sea el AFD $M = (Q, \Sigma, \delta, q_0, F)$ 
Para todo $q \in Q$ y $\alpha, \beta \in \Sigma^*$,

Si $(q, \alpha \beta) \vdash (q,\beta)$ entonces $\forall i \geq 0, (q, \alpha^i \beta) \vdash^* (q,\beta)$ 