#### Bloque 1 - Núcleo conceptual de la semana

Revisen:
- `Semana2/README.md`
- **Lectura4-Deng**
- **Lectura5-Morin**
- `Semana2/include/ArrayStack.h`
- `Semana2/include/FastArrayStack.h`
- `Semana2/include/RootishArrayStack.h`
- `Semana2/include/DengVector.h`

Respondan:

1. Expliquen con sus palabras qué significa que un arreglo use **memoria contigua**.
Significa que todos sus elementos están almacenados uno junto al otro en la RAM, visto de otra forma:
- El primer elemento está en una dirección base.
- El elemento siguiente está en la dirección base + tamaño del tipo.
- El siguiente, en base + 2 * tamaño, y así sucesivamente. 

2. Expliquen por qué acceder a `A[i]` es una operación de costo `O(1)`.
3. Expliquen la diferencia entre `size` y `capacity`.
4. Expliquen por qué un arreglo dinámico no puede crecer "en el mismo sitio" y necesita reservar un bloque nuevo al hacer `resize()`.
5. Expliquen por qué duplicar capacidad permite defender costo amortizado `O(1)` para inserciones al final.
6. Comparen `ArrayStack` y `DengVector`: ¿qué comparten y qué cambia en interfaz o intención didáctica?
7. Expliquen qué mejora `FastArrayStack` respecto a `ArrayStack`.
8. Expliquen cuál es la idea espacial central de `RootishArrayStack`.
9. Expliquen por qué `RootishArrayStack` usa bloques de tamaños `1, 2, 3, ...`.
10. Expliquen qué relación hay entre representación, costo temporal y desperdicio espacial en estas estructuras.
