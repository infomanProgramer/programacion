# Análisis de Algoritmos

Analizar un algoritmo significa predecir los recursos que este requiere, entre los cuales se debe considerar:

- Memoria
- Ancho de banda
- Consumo de energía

En la mayoría de los casos, el recurso más importante a considerar es el ***tiempo de ejecución***. 

Cuando analizamos un algoritmo, necesitamos un modelo de la tecnología sobre la que se ejecuta, incluidos los recursos de esa tecnología y como se expresan en costos

Cuando decimos que un algoritmo tarda $O(n)$, $O(n^2)$, etc, no estamos midiendo una computadora real especifica. En cambio usamos un modelo teórico llamado **RAM (Random Access Machine)** en este modelo se supone que operaciones simples como:

- Suma
- Resta
- Multiplicación
- División
- Comparación
- Asignación de valores
- Acceso a una posición de memoria

tienen un costo constante, es decir, que toman un tiempo $O(1)$.

Cuando trabajamos con entradas de *tamaño n*, asumimos que los enteros estan representados por: $$c \log_2 n$$ bits. 

Donde:

- $c$ es una constante *mayor o igual a 1*
- $\log_2 n$ es el número de bits necesarios para representar el valor de $n$

**Por ejemplo:**

Si $$n = 1000$$ entonces $$\log_2(1000) = 10 \text{ bits}$$

Con 10 bits podemos representar números entre 0 y 1023. Asi podemos guardar indices desde 0 hasta 999 y acceder a cualquier posición del arreglo.

C es una constante para que el tamaño de la palabra no crezca arbitrariamente (Si el tamaño de la palabra pudiera crecer arbitrariamente, podríamos
almacenar enormes cantidades de datos en una sola palabra y operar con todo ello en tiempo constante un
escenario irreal.


#### La zona gris del modelo RAM**

El modelo RAM simplifica muchas cosas, por ejemplo:

- ¿La suma esta constante? Si
- ¿La comparación es constante? Si

Pero aparecen dudas en operaciones mas complejas como en la ***Exponenciación***

**¿La Exponenciación cuesta tiempo constante?**

No, por ejemplo tomemos $2^{1000}$. No es razonable pensar que una computadora obtiene el resultado en un solo paso. Para calcular la potencia se necesitan varias multiplicaciones

De hecho, usando exponenciación rápida, el número de multiplicaciones es aproximadamente: $$O(\log n)$$
Por ejemplo: $$2^{16}$$
se puede calcular como:
$$2^{16} = (2^8)^2 = ((2^4)^2)^2 = (((2^2)^2)^2)^2$$
Por eso el tiempo depende de *n* y no es constante





