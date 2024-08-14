```mermaid
graph TD;
    A((A)) --> |texto| C;
    A-->B((B));
    B-->D((D));
    C((C))-->D;

    
    style A fill:#ff,stroke:#333,stroke-width:4px;
    linkStyle 0 stroke:#f00,stroke-width:2px;
    linkStyle 1 stroke:#0f0,stroke-width:2px;
    linkStyle 2 stroke:#00f,stroke-width:2px;
    linkStyle 3 stroke:#ff0,stroke-width:2px;
```

En este ejemplo:

- `linkStyle 0 stroke:#f00,stroke-width:2px;` hace que la primera flecha sea roja (`#f00`).
- `linkStyle 1 stroke:#0f0,stroke-width:2px;` hace que la segunda flecha sea verde (`#0f0`).
- `linkStyle 2 stroke:#00f,stroke-width:2px;` hace que la tercera flecha sea azul (`#00f`).
- `linkStyle 3 stroke:#ff0,stroke-width:2px;` hace que la cuarta flecha sea amarilla (`#ff0`).

Puedes ajustar los colores y el ancho de las líneas según tus necesidades. 


```mermaid
graph TD;
    A["$$E = mc^2$$"] --> B["$$ a^2 + b^2 = c^2 $$"];
    C["Nodo con $$\int_a^b f(x)\, dx$$"] --> D["Fórmula: $$ x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$$"];

```
En este ejemplo:

- Los nodos `A`, `B`, `C`, y `D` contienen fórmulas en LaTeX.
- Las fórmulas están encerradas entre `\( \)` para el modo en línea, pero también podrías usar `$$ $$` para ecuaciones en bloque si el entorno lo soporta.

### Consideraciones:

1. **Compatibilidad:** Asegúrate de que la plataforma donde estás usando Mermaid soporta la renderización de LaTeX. Algunas plataformas, como GitHub y algunos editores Markdown, pueden no renderizar LaTeX dentro de Mermaid directamente.
   
2. **Alternativa:** Si necesitas asegurarte de que las fórmulas se rendericen correctamente en todas las plataformas, considera usar imágenes generadas de las fórmulas y referenciarlas en los nodos en lugar de texto LaTeX.

```mermaid
graph TD;
    A["\(E = mc^2\)"] --> B["\(a^2 + b^2 = c^2\)"];
    C["Nodo con \(\int_a^b f(x)\, dx\)"] --> D["Fórmula: \(x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}\)"];
```