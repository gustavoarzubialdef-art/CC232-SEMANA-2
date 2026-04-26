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
- El primer elemento está en una **dirección base**.
- El elemento siguiente está en la **dirección base + tamaño del tipo**.
- El siguiente, en base + 2 * tamaño, y así sucesivamente. 

2. Expliquen por qué acceder a `A[i]` es una operación de costo `O(1)`.
Porque los arreglos utilizan memoria contigua, lo que permite calcular la dirección de memoria del elemento i de manera directa y constante. Específicamente, la dirección se obtiene como **dirección base + i * tamaño del elemento**

3. Expliquen la diferencia entre `size` y `capacity`.
- size: Representa el número de elementos actualmente almacenados en la estructura.
- capacity: Representa el espacio total reservado en memoria para el arreglo subyacente.
size es el espacio utilizado mientras que capacity es el espacion total.

4. Expliquen por qué un arreglo dinámico no puede crecer "en el mismo sitio" y necesita reservar un bloque nuevo al hacer `resize()`.
Porque el bloque adyacente en memoria podría estar ocupado por otros datos o procesos, impidiendo la expansión contigua.

5. Expliquen por qué duplicar capacidad permite defender costo amortizado `O(1)` para inserciones al final.
6. Comparen `ArrayStack` y `DengVector`: ¿qué comparten y qué cambia en interfaz o intención didáctica?
7. Expliquen qué mejora `FastArrayStack` respecto a `ArrayStack`.
8. Expliquen cuál es la idea espacial central de `RootishArrayStack`.
9. Expliquen por qué `RootishArrayStack` usa bloques de tamaños `1, 2, 3, ...`.
10. Expliquen qué relación hay entre representación, costo temporal y desperdicio espacial en estas estructuras.

#### Bloque 2 - Demostración y trazado guiado

Revisen:
- `Semana2/demos/demo_array_basico.cpp`
- `Semana2/demos/demo_arraystack.cpp`
- `Semana2/demos/demo_arraystack_explicado.cpp`
- `Semana2/demos/demo_fastarraystack.cpp`
- `Semana2/demos/demo_rootisharraystack.cpp`
- `Semana2/demos/demo_rootisharraystack_explicado.cpp`
- `Semana2/demos/demo_deng_vector.cpp`
- `Semana2/demos/demo_stl_vector_contraste.cpp`

Construyan una tabla con cuatro columnas:

- Archivo
- Salida u observable importante
- Idea estructural
- Argumento de costo o espacio

Luego respondan:

1. En `demo_array_basico.cpp`, ¿qué deja claro sobre arreglo, longitud y asignación?
2. En `demo_arraystack_explicado.cpp`, ¿qué operación muestra mejor el costo por desplazamientos?
3. En `demo_fastarraystack.cpp`, ¿qué cambia en la implementación aunque no cambie la complejidad asintótica?
4. En `demo_rootisharraystack_explicado.cpp`, ¿qué ejemplo explica mejor el mapeo de índice lógico a bloque y offset?
5. En `demo_deng_vector.cpp`, ¿qué observable permite defender el crecimiento de `capacity`?
6. En `demo_stl_vector_contraste.cpp`, ¿qué similitud conceptual observan con `DengVector`?
7. ¿Qué demo sirve mejor para defender **amortización** y cuál sirve mejor para defender **uso de espacio**?

#### Bloque 3-Pruebas públicas, stress y correctitud

Revisen:
- `Semana2/pruebas_publicas/README.md`
- `Semana2/pruebas_publicas/test_public_week2.cpp`
- `Semana2/pruebas_internas/test_internal_week2.cpp`
- `Semana2/pruebas_internas/resize_stress_week2.cpp`

Respondan:

1. ¿Qué operaciones mínimas valida la prueba pública para `ArrayStack`?
2. ¿Qué operaciones mínimas valida la prueba pública para `FastArrayStack`?
3. ¿Qué operaciones mínimas valida la prueba pública para `RootishArrayStack`?
4. ¿Qué sí demuestra una prueba pública sobre una estructura?
5. ¿Qué no demuestra una prueba pública?
6. En `resize_stress_week2.cpp`, ¿qué comportamiento intenta estresar sobre crecimiento, reducción o estabilidad?
7. ¿Por qué pasar pruebas no reemplaza una explicación de invariantes y complejidad?

#### Bloque 4-Vector como puente entre teoría y código

Revisen:
- `Semana2/include/DengVector.h`
- `Semana2/demos/demo_deng_vector.cpp`
- **Lectura4-Deng**

Respondan:

1. ¿Qué papel cumplen `_size`, `_capacity` y `_elem`?
2. ¿Cuándo debe ejecutarse `expand()`?
3. ¿Por qué `insert(r, e)` necesita desplazar elementos?
4. ¿Qué diferencia conceptual hay entre `remove(r)` y `remove(lo, hi)`?
5. ¿Qué evidencia de copia profunda aparece en la demo?
6. ¿Por qué `traverse()` es una buena interfaz didáctica?
7. ¿Qué ventaja tiene implementar un vector propio antes de depender de `std::vector`?

#### Bloque 5 - RootishArrayStack: espacio y mapeo

Revisen:
- `Semana2/include/RootishArrayStack.h`
- `Semana2/include/RootishArrayStackExplicado.h`
- `Semana2/demos/demo_rootisharraystack.cpp`
- `Semana2/demos/demo_rootisharraystack_explicado.cpp`
- **Lectura5-Morin**

Respondan:

1. ¿Cómo se distribuyen los elementos entre bloques?
2. ¿Por qué con `r` bloques la capacidad total es `r(r+1)/2`?
3. ¿Qué problema resuelve `i2b(i)`?
4. ¿Qué información produce `locate(i)` en la versión explicada?
5. ¿Qué se gana en espacio frente a `ArrayStack`?
6. ¿Qué se conserva igual respecto a la interfaz?
7. ¿Qué parte les parece más difícil de defender oralmente: el mapeo, el análisis espacial o el costo amortizado de `grow/shrink`?

#### Bloque 6-Refuerzo de lectura

Revisen:
- **Lectura4-Deng**

Respondan brevemente:

1. ¿Qué aporta `operator[]` a la idea de vector?
2. ¿Qué supone `find(e)` sobre igualdad entre elementos?
3. ¿Qué muestra `traverse()` sobre procesamiento uniforme de toda la estructura?
4. ¿Por qué esta lectura sirve como refuerzo natural de `DengVector` aunque no sea el centro exclusivo de la semana?

#### Bloque 7 - Cierre comparativo

Respondan esta pregunta final:

**¿Qué cambia cuando pasamos de "usar un arreglo" a "diseñar una estructura dinámica basada en arreglo"?**

La respuesta debe incluir obligatoriamente:
- una afirmación sobre representación
- una afirmación sobre correctitud
- una afirmación sobre costo amortizado
- una afirmación sobre uso de espacio
- una comparación entre `ArrayStack`, `FastArrayStack` y `RootishArrayStack`.
