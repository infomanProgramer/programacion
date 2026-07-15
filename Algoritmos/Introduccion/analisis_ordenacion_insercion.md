# Análisis de la Ordenación por Inserción

**¿Cuanto tiempo tarde el procedimiento INSERTION-SORT?**

Una forma de averiguarlo es ejecutarlo en tu ordenador y cronometrarlo.

**¿Qué tipo de información te proporcionaria esta prueba de tiempo de este tipo?**

Tiempo exacto en tu ordenador, con esa entrada especifica con:

- Compilador o interprete especifico que utilizaste
- Tareas de segundo plano de tu sistema operativo

**¿Qué pasaria si lo ejecutamos con otra entrada o en un ordenador diferente?**

No mucho

Por lo que en lugar de cronometrar una o varias ejecuciones, podemos determinar su tiempo analizando el algoritmo en sí mismo.

- Examinaremos cuantas veces se ejecuta cada lina del pseudocódigo
- Cuanto tiempo tarda cada linea en ejecutarse

Desarrollaremos una formula precisa, aunque compleja para calcular el tiempo de ejecución. Luego simplificaremos la parte importante de la formula utilizando una notación práctica que nos permita comparar los tiempo de ejecución de diferentes algoritmos para el mismo problema

**¿Como analizaremos la ordenación por inserción?**

- Primero reconocer que el tiempo de ejecución dependerá de la entrada
- Las medidas de tiempo pueden variar si al ordenar dos matrices del mismo tamaño una esta mas ordenada que otra.

Aunque el tiempo de ejecución puede depender de muchas caracteristicas de la entrada, nos enfocaremos en las que tienen mayor efecto, el tamaño de la entrada y describiremos el tiempo de ejecución en función del tamaño de la entrada. Para ello necesitamos describir con mas precisión los terminos:

- **Tamaño de la entrada**: Numero de elementos que se van a ordenar
- **Tiempo de ejecución**: Numero de operaciones elementales que se realizan

Tambien necesitamos aclarar si estamos hablando del tiempo de ejecución para una entrada o que produce el peor caso, el mejor caso o algún otro caso.

La mejor manera de medir el tamaño de la entrada depende del problema que se esté estudiando. Por ejemplo:

- Para problemas, como la *ordenación* o el *calculo de las transformadas discretas de Fourier*, la medida mas natural es el numero de elementos de la entrada. 
- Otros, como la *multiplicación de dos números enteros*, la mejor medida del tamaño de la entrada es el número total de bits necesarios para representarla en notación binaria. 
- Otras veces es mas apropiado describir el tamaño de la entrada con mas de un número

Por ejemplo, si la entrada de un algoritmo es un grafo, solemos caracterizar su tamaño tanto por el número de vertices como por el número de aristas.

## Tiempo de ejecución

![alt text](image-1.png)

Fuente:

- Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). Introduction to Algorithms (3rd ed.). The MIT Press.


El tiempo de ejecución de un algoritmo es determinada por el número de instrucciones y accesos a datos ejecutados. La forma de contabilizar estos costos debe ser independiente de cualquier ordenador en particular, pero dentro del modelo RAM. Asumiendo que cada ejecución de la k-esima linea tarda $c_k$ tiempo, donde $c_k$ es una constante.

Sin embargo, esta formula resulta ser compleja. Por lo tanto, utilizaremos una notación más simple, concisa y facil de usar. Esta notación permite comparar claramente los tiempos de ejecución de los algoritmos, especialmente a medida que aumenta el tamaño de entrada

Para analizar el procedimiento de ordenación por inserción, veamos la siguiente pagina, con el tiempo de ejecución de cada instrucción y el número de veces que se ejecuta. Para cada: 
$$i = 2, 3, ....., n$$
Sea $t_i$ el número de veces que se ejecuta la prueba del bucle *while* en la linea 5 para cada valor de *i*. Cuando el bucle *for* o *while*  finaliza de la forma habitual (porque la prueba en la cabecera del bucle es FALSA), la prueba se ejecuta una vez más que el cuerpo del bucle. Dado que los comentarios no son instrucciones ejecutables, supongamos que no consumen tiempo.

El tiempo de ejecución del algoritmo es la suma de todos los tiempos de ejecución de cada instrucción. Una instrucción que requiere $c_k$ pasos para ejecutarse y se ejecuta $m$ veces contribuye con $c_k \cdot m$ al tiempo de ejecución total. El tiempo de entrada de ejecución de un algoritmo con una entrada de tamaño $n$ suele denotarse como $T(n)$. Para computar $T(n)$, el tiempo de ejecución de INSERTION-SORT en una entrada de $n$ valores, sumamos los productos del costo y columnas de tiempo, obteniendo:

$$T(n) = c_1n + c_2(n-1) + c_4(n-1) + c_5(n-1) + c_8(n-1) = (c_1 + c_2 + c_4 + c_5 + c_8)n - (c_2 + c_4 + c_5 + c_8)$$

Podemos expresar este tiempo de ejecución como $an+b$ para las constantes a y b que dependen en costos declarados $c_k$ donde $a = c_1+c_2-c_5+c_8$ y $b=c_2+c_4+c_5+c_8$. El tiempo de ejecución es una funcion lineal de $n$.

El peor caso se produce cuando el array esta inverso. Ya que el procedimiento debe comparar cada elemento $A[i]$ con cada elemento en el subarreglo ordenado $A[1:i-1]$ y $t_i = i$ para $i = 2, 3, ..., n$, (El procedimiento encuentra que $A[j] > key$ cada vez en la linea 5) que ya esta en orden inverso y el bucle while finaliza solo cuando j llega a 0. Observando que:

$$\sum_{i=2}^{n} i=(\sum_{i=1}^{n} i) - 1=\frac{n(n+1)}{2} - 1$$



Pagina 53 / 1312