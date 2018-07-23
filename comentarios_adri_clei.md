---
title: Paper CLEI 2018 de Adriana y Monserrat
---

# Review 1
---------------
> - Según la bibliografía, la investigación es una extensión del trabajo
de L.G. More & M.A. Brizuela, pero no se discute la comparación de
resultados, esto es recomendable para hacer notar el avance de
investigación.

**El trabajo es un caso general del trabajo de lmore y brizuela
Los resultados del trabajo de lmore y brizuela caen en el frente pareto del trabajo, en la esquina cuay solución corresponde a la mínima similaridad. No se consideraron pruebas experimentales debido a que los enfoques son diferentes.**

> ~~- Se observa buena representación y discusión de los resultados con
tablas y gráficas. En las conclusiones se sugiere profundizar más. - No
mencionan como determinaron los valores de los dos parámetros del
algoritmo CLAHE, que son: Block Size y Clip Limit, según la bibliofrafía
del tema.~~

> - El artículo está bien estructurado y completo. Aunque el título hace
referencia a un nombre diferente de algoritmo de optimización
multiobjetivo que no se menciona en el cuerpo del artículo. Las
abreviaturas o nombres de algoritmos se referencian a su respectivo
autor desde el primer momento en que se mencionan, tal es el caso de
SMPSO en el 7mo párrafo de la Introducción. Arreglar idioma del resumen
y palabras clave.

**Agregar el pseudocódigo de smpso-clahe y un párrafo explicativo indicando cuál es la entrada de datos, la salida y lo que se realiza en cada línea.**

# Review 2
---------------

> ~~¿Cuál es el sentido del título en inglés y el texto en español? El
Conjunto Pareto por ser nombre propio debe ser escrito en letra
mayúscula. Se trata de un trabajo 100% práctico de encontrar cuál es la
mejor métrica que se adapta a los fines esperados. Durante la lectura me
quedé en la duda sobre el resultado de las correlaciones. Después de
leer la Tabla I entendí que debería pensar en imágenes radiológicas. A
partir de ahí, entendí el concepto de correlación negativa. No quedó
claro si el proceso adoptado puede ser aplicado para otros procesos de
análisis de imágenes que no los de contraste negativo, así como no quedó
claro porque el proceso SSIM presentó el mejor resultado. Puedo ver
visualmente, sin embargo, un análisis teórico podría contestar si una
radiografía del oído obtendría el mismo éxito.~~

~~**Titulo y abstract deben ir en ingles**~~

~~**En la tabla de correlaciones agregar una explicación de los valores de correlación negativa. Básicamente, una correlación negativa indica que el mejoramiento de una función objetivo se logra a costa del empeoramiento de la otra función objetivo en un contexto de minimización o maximización de ambas. Es decir, son funciones objetivo contradictorias.**~~

~~**Agregar en trabajos futuros, el análisis de desempeño de la propuesta en imágenes de otra naturaleza.**~~

**Los Comentarios arriba expuestos deben verse reflejados en el paper camera ready y en el libro.**

## Comentarios Internos
---------------

### 1. Introducción
-------------------

> ~~Sin embargo, éste y la mayorı́a de los otros métodos de mejora de
contraste pueden producir imágenes de aspecto no naturales,
lo que ocasiona que aquellas obtenidas por estos métodos no
son las deseables.~~

~~Sin embargo, éste y la mayorı́a de los otros métodos de mejora de
contraste pueden producir imágenes de aspecto no naturales no natural,
lo que ocasiona que aquellas obtenidas por estos métodos no son las deseables sean las deseables.~~

### 2. MÉTRICAS DE EVALUACIÓN DE IMÁGENES
-------------------

~~En la ecuación 1, $\mathscr{H} \in []$, debe ir con corchetes.~~


~~* En 2B, *** ojo con la nomenclatura *** pusieron $M \times N$ para definir tamaño de una vecindad, pero da a entender que la vecindad es toda la imagen, porque usan también $M \times N$ para definir el tamaño de toda la imagen.~~

Luego de la ecuación 1, no se definen n_k ni Z

En la ecuación 2, hay dos temas que necesitan revisión:
1. debería definirse n_k con otra nomenclatura, porque no es el mismo n_k de la ecuación 1
2. E(vij) debería ser E(I), es decir de toda la imagen. Ahora mismo da a entender que la entropía local se aplica solamente a una vecindad. Ahora bien, ¿todas las entropías locales se promedian, o cómo se obtiene la entropía local final? Debe quedar claro en la ecuación 2.

### 3. Planeamiento del problema
--------------------------------
~~> En el tratamiento de imágenes, frecuentemente es necesario
detectar caracterı́sticas de interés que pueden ser utilizadas
para un análisis posterior,~~

~~En el tratamiento de imágenes, frecuentemente es necesario
detectar caracterı́sticas de interés que pueden ser utilizadas
para un análisis posterior,~~

> CLAHE es  un  refinamiento  de AHE
Falta citación para AHE

> \begin{equation}\label{restriccion}
>    \kappa   = \frac{2}{2 - \sigma - \sqrt[]{ \sigma^2 - 4 \sigma}}
>\end{equation}

¿qué son los sigma en la ecuación 11?

### 4. Proupesta
-----------------
> ~~Se buscan métricas que aporten valores más cercanos a la
realidad,~~

~~?~~

> ~~Dados la imagen de entrada f 1 , en escala de gris de tamaño
M × N y el algortimo CLAHE, se desea calcular la mejor
solución que nos indique que dichas métricas son altamente
contradictorias, minimizando la combinación de las funciones
objetivos T A y T B , tal que:~~

~~Dados la imagen de entrada f 1 , en escala de gris escala de grises de tamaño
M × N y el algortimo CLAHE, se desea calcular la mejor
solución que nos indique que dichas métricas son altamente
contradictorias, minimizando la combinación de las funciones
objetivos funciones objetivo T A y T B , tal que:~~

> ~~Se incorpora un mecanismo de restricción 10 sobre la
ecuación 9 para limitar la velocidad máxima de las partı́culas
y mejorar la capacidad de búsqueda del algoritmo [2].~~

~~Se incorpora un mecanismo de restricción 10 (véase Ecuación 10) sobre la
ecuación 9 para limitar la velocidad máxima de las partı́culas
y mejorar la capacidad de búsqueda del algoritmo [2].~~

> De manera a obtener Frentes de Pareto Robusto de acuerdo
a la ecuación 15.

Nuevamente no hay citaciones que ayuden a sentar la teoría de Optimización Robusta.

En la propuesta, puse un diagrama para tratar de entender mejor el proceso de pso-clahe robusto. Ahora mismo necesita refinar, es un bosquejo inicial.

### 5. Resultados y Discusión
-----------------

> ~~Se analizó el comportamiento del Conjunto Pareto resultante
de cada imagen procesada, al considerar como una sola entrada
el conjunto de todas las imágenes y realizar el cálculo de la
Entropı́a Local II-B y SSIM II-C entre todas las imágenes; de
esta forma se obtuvo el Frente Pareto Robusto; y se consideró
el Frente Pareto óptimo de una imagen f , como el Frente
Pareto de las N-1 imágenes y se obtuvo el Frente Pareto
Promedio de la imagen f como se observa en la Figura 3.~~

~~El párrafo no se entiende bien~~

Es necesario explicar qué se contrasta al poner los plots de frente pareto robusto versus frente pareto óptimo. OJO ESTO ES IMPORTANTE, de manera a entender las gráficas 

También, ¿los frentes pareto robustos no deberían ser iguales en todos los ploteados? o no se entiende nomás bien por los tamaños de las figuras

Las imágenes originales también tienen ssim y entropía local, es necesario agregar a todas las figuras para comparar mejor.

por qué usaron resultados que salieron de optimizar con entropía/ltg, y después otros resultados que salieron de optimizar con entropía/ssim?

### VI.C ONCLUSIONES Y T RABAJOS F UTUROS
------------------------------------------

> ~~Tabla II: Promedio de la correlación de Pearson.~~

~~Ésta tabla no debería ir en las conclusiones, más bien en la discusión.~~

> Al analizar los Frentes Paretos óptimos de las imágenes
procesadas, se observa que la solución óptima de una imagen
f no necesariamente es la mejor solución para una imagen f 0 .

Éste análisis tampoco debería ir en la conclusión.